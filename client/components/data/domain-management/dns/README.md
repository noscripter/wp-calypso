DnsData
=======

A component that fetches a domain's DNS related data and passes it to its children.

## Usage

Pass a component through the `component` prop of `<DnsData />`. `DnsData` will pass data to the given `component` prop, which is mounted as a child.
It will handle the data itself thus helping us to decouple concerns: i.e. fetching and displaying data. This pattern is also called [container components](https://medium.com/@learnreact/container-components-c0e67432e005).

```js
import React from 'react';
import DnsData from 'components/data/domain-management/dns';
import MyChildComponent from 'components/my-child-component';

// initialize rest of the variables

const MyComponent = React.createClass( {
	render() {
		return (
			<DnsData
				component={ MyChildComponent }
				selectedDomainName={ selectedDomainName }
				sites={ sites } />
		);
	}
} );

export default MyComponent;
```

The component expects to receive all listed props:

* `component` - mentioned above
* `selectedDomainName` - the domain name currently selected 
* `sites` - a list of user sites 

The child component should receive processed props defined during the render:

* `selectedDomainName` - the domain name currently selected 
* `selectedSite` - the site currently selected  

As well as:

* `domains` - a list of domains, it's the result of a call to `DomainsStore.getForSite` for the current site
* `dns` - DNS records, it's the result of a call to `DnsStore.getByDomainName` for the current domain  

It's updated whenever `DomainsStore`, `DnsStore` or `sites` changes.

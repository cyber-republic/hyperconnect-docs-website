# Use Cases Overview

The modular architecture of the HyperConnect Framework provides a solid base for any industry vertical within the Internet-of-Things.

Blockchain technology and the underlying peer-to-peer network allow the secure exchange of Internet-of-Things data between devices as well as value exchange for third-party services while preserving the anonymity of their users.

The exchange of data ownership or service against monetary value occurs on a decentralized and immutable ledger, based on smart contracts, while the transfer of files is carried out via the peer-to-peer network and distributed file storage.


## Smart Home

The Internet-of-Things, including Smart Homes, has the potential to make lives easier with automation and remote control. Until now, however, users had to trade convenience for privacy and security. HyperConnect puts data and control in the user's hands.

HyperConnect is the complete Smart Home solution connected via Peer-to-Peer communication. Without the need of a central server, data access and control is only possible to the owner.


*Problems to be solved:*

- Many Smart Home manufacturers do not follow standard security procedures.
- Users cannot evaluate the security of the products due to closed source software.
- Connection and authentication of products always happens in a centralized manner.
- Data is most often stored in a centralized manner.
- Privacy is harmed as soon as the product data can be 'connected/matched' with user persona.
- Data loss or exposure is harmful by itself, but unwanted remote control is a real threat.
- Secure solutions are often very complex and need technical skills and dedication to keep up-to-date.
- Complex solutions are expensive and hard to market.


*Solution:*

- HyperConnect allows the usage of a complete Smart Home solution connected via Peer-to-Peer communication.
- Without the need of a central server, data access and control is only possible to the owner.
- Fully open source and available for anyone to review the code.
- Hardware agnostic, can be used with any device and smart phones.
- Authentication happens within the network, no need for separate systems.
- Full privacy with only local storage of your own data.
- Fully customizable to match any requirement.
- Free to use.



## Anonymous data collection

*Note: Experimental, needs further development on blockchain level.*

Manufacturers are keen to know more about their own products. How their products are being used, which elements need replacement, which ones are faulty in general or which ones are even dangerous. To this day, most of this data is collected after the product is being sent back to the manufacturer for repair. Manufacturers have to make estimations of these statistics and often risk negative feedback from customers or get involved in lawsuits.
The secure collection of usage data from products without having to expose identities is the most optimal solution to this massive problem that manufacturers are currently facing.

*Solution:*

During production of the devices, a modified Elastos Carrier is installed on products and a decentralized ID is generated for each device.
The carrier is programmed to automatically send a request to a fixed decentralized ID
when first joining the network. The fixed decentralized ID belongs to the manufacturer and acts as a gateway to collect data in message form.
The manufacturer does not have control over the automatically generated IDs and cannot identify which product has which decentralized ID.
When a product is delivered to the consumer, the product accesses the internet and starts sending data to the decentralized ID that belongs to the manufacturer.
The received messages through the modified Elastos Carrier can then be exported by the manufacturer for creating statistics and other purposes.

The benefit of this process is that IDs are generated for each product and are programmed to contact only one DID in the network, and that DID belongs to the manufacturer.

The manufacturer has no possibility of matching the device DIDs with their customers by default as the IDs were generated in a ‘black box’ environment from a viewpoint of the manufacturer.

Privacy of the consumers is fully preserved. The peer-to-peer network used for communication is secure by its nature.

An additional benefit to this solution is that if the customer, for any reason, wants to make the link between his or her identity as a customer and the device’s identity, the customer can provide the DID of the product to the manufacturer and the manufacturer can trace back all the information even from the past about the product. This enables an improved, professional service for the manufacturer without requiring excessive input from the customer side.

If required, manufacturers may also utilize the distributed file storage IPFS for secure software updates on products.

HyperConnect extends the capabilities of the Elastos Carrier, introduces the manufacturing process and the node implementation for the Carrier on the manufacturer side.


## Anonymous third-party service usage

*Note: Experimental, needs further development on blockchain level.*

The exchange of data while preserving privacy becomes more complex when an additional monetary layer is required . Monetary value in exchange for a service is an essential real world process that in terms of the Internet-of-Things must follow the same process. The complexity is amplified by the need of total automation, security and preservation of privacy.

As an example, a third party service needs to be used to extend the capabilities of a an Internet-of-Things device. Let us assume that a device transforms speech (audio) into text locally, but there is a need to have the text translated into another language by a third-party service as our device does not have the capability for the translation.

The general idea is that devices will be able to hold small amounts of tokens themselves that can be managed and monitored via the HyperConnect Dapp, and the services. When a service is selected to be used by a device, the device sends the required amount of tokens to the service provider address, which in return accepts the invitation of the device to connect for a fixed time frame, depending on the value of the tokens transferred. Because the transfer of tokens involves costs, the optimal time frames may be days, weeks or months to use the service.

The HyperConnect Dapp would provide the Marketplace for third-party services to allow device subscriptions in return of HyperConnect tokens.

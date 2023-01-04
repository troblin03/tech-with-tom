# Cloud Service Models

An application deployed anywhere will typically require an infrastructure stack. This is a list of things the application needs stacked on top of each other.

Any implementation of an infrastructure stack will have parts that you manage, and some parts that somebody else manages.

![Screenshot 2023-01-04 at 15 18 32](https://user-images.githubusercontent.com/54938676/210587922-2d503a2b-b78e-4232-8bf8-f06b62e33611.png)

## On-premises system

Your business owns everything on its premises. Whilst this is imaginably expensive, it also offers the most flexibility. In theory, you can create systems which are tailor made to your own needs.

###### DC Hosted

Prior to cloud computing, data centre hosted was an on-premises infrastructure, however the data centre was in a building managed by an external vendor.

## Infrastructure as a Service (IaaS)

In this model, the facilities, infrastructure, servers, and virtualisation of the infrastructure stack are all provided for you. You consume the O/S and manage anything upwards.

IaaS is generally charged per second for use of the virtual machine. The largest costs are covered by the vendor. You do lose a bit of flexibility, but you get a substantial reduction in cost and risk.

## Platform as a Service (PaaS)

With PaaS, you consume the runtime environment. You manage your application and its data, whilst consuming the runtime. Essentially something like Heroku, that developers use to host an application vs self hosting.

## Software as a Service (SaaS)

You consume the application, and don't worry about anything else. For example, Netflix, g-mail, Dropbox etc..

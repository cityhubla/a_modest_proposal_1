# A modest proposal

The [Los Angeles Housing Department](http://hcidla.lacity.org/Is-My-Rental-Unit-Subject-to-the-RSO) has provided the public with the means to find out if their home is rent-stabilized under the Rent Stabilization Ordinance.

![RSO Page](/images/lacity_rso-01.png)

The drawback to this and after 3 steps from the mainpage of the Department's website is that it leads you to the City of Los Angeles's Planning Department's [ZIMAS tool](http://zimas.lacity.org/), a map that provides planning and zoning information on a particular property.

![ZIMAS Page](/images/lacity_rso-02.png)

The problem with using this tool is that while it will give you the answer if your home is rent-stabilized, it is also very dense with other information that is not relevant and in only one language. And after you get the answer, then what? What are my rights if my home is rent-stabilized? One has to go back to the Housing Department's page to find it.

![ZIMAS results](/images/lacity_rso-03.png)

So here's a modest proposal. Given that ZIMAS is the only tool available that provides information, it's outdated interface would be difficult to change to retrieve specific information. What if we just load the tool in an `iframe` within a simple HTML page with an interface that interacts with ZIMAS behind the scenes?

![iframe](/images/lacity_rso-04.png)

It could be as simple as just having the user select the language of their choice and fill in their home address. The result is just a simple Yes or No with a link directing them to their rights as a renter.

![example](/images/lacity_rso-05.png)

A method would be to use jQuery to access and fill the input to the unique ids of the ZIMAS page, wait for some result and return the response from the id specific to rent-stabilization.

![method](/images/lacity_rso-06.png)

This would be possible if this simple page was loaded on the same server so that there is no issue with the Cross Origin Resource Sharing (CORS) mechanism in place on our web browsers. There would be no change to the ZIMAS code.

The other alternative would be for the Housing Department to upload the RSO data to LA's amazing Open Data Portals.

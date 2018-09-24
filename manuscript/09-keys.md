# Choose great keys
We have seen in Chapter XX that _keys_ are what you use to refer to entities in other tables. A _primary key_ is the unique identifier of each observation in your table, a _foreign key_ is pointing to other entities in another table. For example, the tables below show a many-to-many relation between firms and managers. The `firm_id` is the primary key of the `firm` table, whereas `person_id` is the primary key of the `person` table. Both are foreign keys in the `manage` table, which lists the time spells during which manager with `person_id` manages a particular firm with `firm_id`. (Keys are also called _index_ and _id_.)

A> Example of three tables, referring to one another with foreign keys. `firm` - `manage` - `person`

But how do these keys look in real life? Are they consecutively numbering rows from 1? Can we use names of firms and people as keys? Should we use cryptographic hash functions to generate [universally unique identifiers](https://en.wikipedia.org/wiki/Universally_unique_identifier)? Often you will have this decided for you with keys already given in the data store in which you are loading your data. This chapter is about the trade-offs when you get to make the choice yourself.

## Names are not unique

Most importantly, keys should be _unique_, that is, no two different observations should receive the same key. This sounds obvious, but your design can make this requirement harder or easier to satisfy. Suppose you decide to refer to users by their last name (an obviously silly idea). After the second `smith` and `jones`, you will have to change your system. Then you decide to add first names. You are safe until the second `john_smith` or `charles_jones`. You'll end up with `john_smith_02`, which is just plain ugly. (And what if there are more than 99 John Smiths's in your data?) 

If you think you would never commit such silly mistakes, read Patrick McKenzie's [list of 40 falsehoods](https://www.kalzumeus.com/2010/06/17/falsehoods-programmers-believe-about-names/) programmers often assume about names. I come from a country which uses the Eastern name order, uses many accented letters, and where wives' married names often do not include their first names (as in "Szabó Jánosné ~ "Mrs John Smith"). I've encountered people with only one name. How hard it is for them to enter their name into any web app or database?

It gets worth with companies and organizations. It is next to impossible to use their correct name more than once. The municipal government of the Budapest district where my university is located is officially called "Belváros-Lipótváros Budapest Főváros V. kerület Polgármesteri Hivatal." How often do you think it is spelled right in databases? Moreover, there are 37 elementary schools in Hungary whose official name is simply "elementary school."

D> better, more international examples?

No, names are not unique, and are a terrible choice for unique keys. This is why most web apps and databases opt for a user chosen alphanumeric userid, an email address, or a computer-generated numeric identifier.

## Verbose keys

Follow these four tips to create useful keys.

1. _If there is a well established identifier for the entity you are describing, use that._ People have Social Security Numbers, firms have Employer Identification Numbers, regions have NUTS or FIPS codes, countries have ISO 3166 codes. Do not invent your own key unless you absolutely have to. 
2. _Your key should be human readable, not just machine readable._ A sequentially increasing integer ID is not very helpful. Nor is an SHA1 has has such `dc6e5923f968db05aee116d94d1792385a9fcca8`. Depending on context, combining 2-3 letters and 8-10 digits works best.
3. _Keys for one type of entity should be easily distinguishable from keys for another type of entity._ When you look at a key, you should immediately see what entity it refers to. Everyone knows `08540` is a ZIP-code and `770-10-2831` is a Social Security Number. 
4. _Use hyphens or other punctuation to denote hierarchy in keys._ The ZIP+4 code `53075-1108` clearly delineates the 5-digit ZIP code from the 4-digit routing number. URLs are the best example of hierarchical keys: `leanpub.com/dataarchitecture` refers to this particular book, but you can use this structure to generate keys for other LeanPub books.


A> ## Example keys for firms and people
A> `F-DE-01234567` is a German firm. `F-HU-12345678` is a Hungarian firm. (Note the use of 2-letter ISO-3166 country codes.) `P-1234567890` is a person.

companies
	:tax identifier, EIN, EU VAT identifier, Open Corporates ID
individuals
	:SSN, email address
regions
	:FIPS, NUTS, ZIP-code (although a ZIP code does not refer to an _area_)
countries
	:ISO 3166 standard, 2-letter, 3-letter or numeric identifier


## Hierarchical keys


## Entity Resolution

- Three steps: Normalize, Merge, Propagate



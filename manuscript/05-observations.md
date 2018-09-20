# Relationships between observations

We have seen how entities may be related to one another. Manager may work at firms, firms may be run by managers. But often, observations about entities are not independent, either.

Take, for example, this list of temperature readings from various sensors. The observations in this table are _measurements_. 

E> NASA sensor data here
E> in simple table

Clearly, Morocco is warmer than Iceland. It also seems that, for each region, July is warmer than December. When modeling this data, we want to allow for the fact that measurements on the same sensor, as well as measurement at the same time _belong together_. 

## Grouping observations

The most general relationship is __grouping__. We want to group all measurements of the same sensor together. Then we can analyze measurements _within the group_ (say, variation in temperature over time) and measurements _across groups_ (say, variation in average temperature across sensors). This latter would typically involve some statistical aggregation, as a group can have multiple observations.

If we decide to group observations for analysis, it is important to define the right groups. First, each observation should belong to a group. You have to decide what to do with that sensor in Antarctica (or on the Moon) if you set out to analyze temperatures by country. Second, no observation can belong to more than one group. This we can enforce easily by referring to groups as a variable for each observation using a simple key, such as `sensor_id` or `country_code` above. Third, the level of grouping should be tailored to our analysis. If we are writing a report on broad temperature deviations across countries, the right grouping is probably countries. If we are working on a new algorithm to correct sensor measurement error, the right grouping is probably sensors.

A> Statistical box?
A> Within-group variation relative to mean
A> Across-group variation of means

## Hierarchical grouping

## Time

Another natural relationship among observations is temporal: some may be earlier than others, some may be later, some may happen at the same time. The time stamps in EE above reflect the time at which the measurement was taken.

Time can be recorded as an instant in time, such as the __time stamp__ above. This is the easier case, as the relationship between any two instants is simple. (Notwithstanding complications with time zones. We are also ignoring relativity theory for temporal data analysis.) When observation A has a smaller number in its time stamp than observation B, it simply happened earlier. 

Having time stamps, you can create natural hierarchical groups by grouping observations into days, months, years, etc. There is more time stamps, though

>
> A figure of a timeline
>

__frequency__

__interval algebra__

A practical consideration is __date and time format__. Years, months, days, hours, minutes, seconds and milliseconds can written a myriad ways, and you will encounter each of these in data in the wild. Luckily, there is an ISO standard for dates and times: ISO 8601. When seeing date and time related fields, your _first_ task is always to convert it to ISO 8601.

E> # ISO 8601
E> `2018-09-16T12:10Z`

## Space


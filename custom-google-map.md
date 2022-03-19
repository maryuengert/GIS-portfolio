## Assignment: Build and deploy a custom Google Map for a non-profit organization

### Nonprofit selection and color palette
For this project, I selected to work with the nonprofit [Partners in Health](https://www.pih.org/), a global public health organization that works to deliver vital health care services to impoverished communities. One of their founders, Paul Farmer, passed away recently--he was a major influence on my decision to go into public policy and I thought it would be fitting to dedicate this project to his organization.

<center>

![FMIruK5WQAMLYuo](https://user-images.githubusercontent.com/81482638/159127896-67dccc27-4579-4f06-99ca-b3ceeb3ab4e3.jpg)
  
</center>

Given PiH's website and various photos I found on Twitter, I built the following color palette to use for this project:

<img width="584" alt="Screenshot 2022-03-16 213737" src="https://user-images.githubusercontent.com/81482638/159127918-48127b0c-e9a0-441b-8c35-0313f9a23006.png">

<img width="818" alt="Screenshot 2022-03-16 210551" src="https://user-images.githubusercontent.com/81482638/159127907-01a2d4f5-f1e1-4034-bd0f-96d3a49e7469.png">

![avatars-000733775098-8bua30-t500x500](https://user-images.githubusercontent.com/81482638/159127910-ee22ecfb-e61a-4324-a7ce-032092e98c86.jpg)

My design decisions were based in the concepts of standard GIS convention, simplicity, and legibility. I wanted to create a map that was simple and readable for PiH's users--PiH is a global organization and uses maps on its website, so their users may come to rely on this map heavily to see where PiH is working. Given their global reach, I also wanted to ensure the map was readble at a global extent. 

Some of my design decisions included:
+ using shades of orange, PiH's main brand color, as the dominant color by assigning it to major features such as land masses, parks, and roads
+ using the contrasting purple color to represent water features because it's a cool color and therefore intutively makes sense to users
+ making labels dark with a light halo to increase readability

Below is a screenshot of the finished map. JSON code can be found in my GIS-portfolio repository.

<img width="607" alt="Screenshot 2022-03-19 112421" src="https://user-images.githubusercontent.com/81482638/159127931-8c6ea8c4-8066-46b4-8fd8-007a44416e91.png">

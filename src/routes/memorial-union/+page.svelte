<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
    import TextBlock from "../../components/TextBlock.svelte";
</script>

<Header/>

<Hero
    category="UI/UX Case Study"
    title="UC Davis Memorial Union App"
    role="Design Interactive"
    names='Spring 2023 Cohort'
    textHTML="<p>The Memorial Union (MU) is a central hub of student life at UC Davis that aims to connect students to campus and enrich their experience by providing a space for students to study, snack and socialize. In the span of 6 weeks, our team followed a human-centered design process to create an application that highlights what the MU has to offer and makes relevant information more accessible for students.</p><p>Awarded most Customer Centric UX by panel of industry professionals</p>"
    img="img/memorial-union/header.webp"
/>

<section>

    <TextBlock
        textHTML="<h1>Meet the team</h1>"
        wideimage="img/memorial-union/meetTheTeam.webp"
    />
    <TextBlock
        textHTML="<h1>Identifying the problem</h1>
    <p>Despite the fact that the Memorial Union (MU) is a central location within UC Davis offering a wide variety of services, including the Coffee House (CoHo), food booths, study rooms, and a game room, a significant number of students remain unaware of the full range of amenities available to them at the MU.</p>
    <div class='emphasis-container'>
        <p class='item emphasis'>How might we create a centralized platform to highlight what the MU has to offer and make relevant information more accessible for students?</p>
    </div>"    
    />
    <TextBlock
        textHTML="<h1>Project Timeline</h1>"
        wideimage="img/memorial-union/timeline.webp"
    />
    <h1>Research</h1>
    <TextBlock
        textHTML="<p>We began research by conducting a literature review of the Memorial Union website to gain a deeper understanding of what the MU offers and what its goals are. These two quotes from the website nicely capture the goals of the MU:</p>
        <p>We also organized all of the services into 8 different categories (study, snack, socialize, amenities, student needs, services, student organization, and shopping) to better visualize the different categories. This became useful when deciding which category of services to highlight on our app.</p>"
        img="img/placeholder.svg"
    />

    <TextBlock
        textHTML="<h2>Survey</h2>
    <p>To gain a broad understanding of how students interact with the Memorial Union, we conducted a survey that garnered 66 responses. Nearly all of our responders were UC Davis students, which became the target audience of our app. We had a diverse pool of respondents with students ranging from all academic standings.</p>"
    />

    <TextBlock
        textHTML="<p>We learned from our data that</p>
        <div class='emphasis-container'>
            <p class='item emphasis'>74% of students visit the Memorial Union at least 2x a week</p>
        </div>
        <p>This shows that the MU is a highly utilized space on campus, thus there is a great need for an app that helps students make the most out of their experience at the MU.</p>
        <div class='emphasis-container'>
            <p class='item emphasis'>68% of students were either confident or very confident that they knew the full array of services offered to them at the MU</p>
        </div>
        <p>This was quite surprising to us considering the wide array of services offered at the MU.</p>"
        img="img/memorial-union/whatYear.webp"
    />
    <TextBlock
        textHTML="<p>We found that students mainly use the MU for food and sometimes to study or to visit some of the popular basic needs services such as The Pantry, a student-run organization that provides food and other basic essentials to UC Davis students and staff. Students want to learn most about social events and basic needs services. Here, we faced our first challenge. We needed to decide whether to focus on highlighting popular services or bring awareness to lesser known services.</p>
        <div class='emphasis-container'>
            <div class='item emphasis'>
                <p class='emphasis'>Most used services:</p>
                <ol>
                    <li>Coffee House (57.6%)</li>
                    <li>The Market (40.9%)</li>
                    <li>The Pantry (21.5%) and study rooms (21.2%)</li>
                </ol>
            </div>
        </div>
        <div class='emphasis-container'>
            <div class='item emphasis'>
                <p class='emphasis'>Services students want to learn most about:</p>
                <ol>
                    <li>MU Events (34.8%) and Center for Student Involvement (34.8%)</li>
                    <li>Aggie Reuse Store (30.3%)</li>
                    <li>Study rooms (27.3%)</li>
                </ol>
            </div>
        </div>"
        img="img/memorial-union/rankReasons.webp"
    />
    <h2>Interviews</h2>
    <TextBlock
        textHTML="<p>To gain a deeper understanding of how a range of students interact with the MU, we conducted 17 interviews. Here are some key insights we learned from our interviews:</p>
        <p>Though students mentioned in the survey that they would be interested in learning more about different basic needs services, they elaborated in the interviews that they would like to have access to that information but it is not a priority for them. This is because they only utilize these services when they need them. Thus, we decided to place the emphasis of our app on highlighting popular services rather than helping students learn more about lesser known services since they did not seem interested.</p>"
        img="img/placeholder.svg"
    />

    <h1>Synthesis</h1>
    <h2>Gathering insights</h2>
    <TextBlock
        textHTML="<p>After conducting user research, we gathered our user research insights and categorized them through affinity mapping with the goal of finding the most common user pain points to address and prioritize</p>
        <p>In addition, we created an empathy map with the goal of identifying what our target users would say, do, think, and feel in different types of situations when visiting the Memorial Union.</p>
        <p>From this, we discovered that students mainly visit the Memorial Union to study, eat, socialize, or utilize the several student resources offered at the Memorial Union.</p>"   
        img="img/memorial-union/affinityMap.webp" 
        img2="img/memorial-union/empathyMap.webp"
    />
    <h2>Identifying Pain Points</h2>
    <div class='emphasis-container'>
        <div class='item'>
            <p class="label">Comfort</p>
            <p class='emphasis'>Users’ MU experience is negatively affected by lack of seating availability.</p>
        </div>
        <div class='item'>
            <p class="label">Awareness</p>
            <p class='emphasis'>Despite users’ confidence about common MU services, they remain unaware of the full range of MU services (including MU social events and study rooms).</p>
        </div>
        <div class='item'>
            <p class="label">Efficiency</p>
            <p class='emphasis'>Users waste time at the Coffee House due to lack of information about wait times and menu availability</p>
        </div>
    </div>

    <h1>Ideation</h1>
    <h2>Low-fidelity Wireframes</h2>

    <TextBlock
        textHTML="<p>To address the pain points we identified earlier, we sketched out potential solutions.</p>
        <p>Our solutions include bar charts to indicate how busy an area is and a navigation bar with 5 main pages:</p>
        <ol>
            <li><p>A Map page to provide a map of the MU that highlights its services and amenities</p></li>
            <li>A Study page to bring attention to available study spots and show seating availability for studying in general areas</li>
            <li>A Food page to provide easy access to wait time information with updated menu item stock availability at the Coffee House</li>
            <li>A Social page to share essential information about upcoming social events held at the MU</li>
            <li>A Services page to share essential information about MU services</li>
        </ol>"
        img="img/memorial-union/lofiSketches.webp"
    />

    <h2>Mid-fidelity Prototypes</h2>
    <p class="label">Study</p>
    <TextBlock
        textHTML="<p>To showcase study spots in the MU, we implemented a horizontal scroll layout with card components for easy readability. We included information about seating availability and hours on each card component in addition to buttons that indicated the booking status of each room.</p>
        <p>An important thing to note is that we designed our first version of mid-fidelity wireframes under the impression that any student could book a study room with their choice of seat layout. We later discovered that only leaders of a student organization can book a study room which led to a pivot in user flow for user testing. To be more specific, we got rid of the user flow for booking and only made use of our study home screen and calendar screen during user testing.</p>"
        img="img/memorial-union/midfiStudy.webp"
    />

    <p class="label">Food</p>
    <TextBlock
        textHTML="<p>Our Food tab implements a vertical scroll layout with card components showcasing important information like hours and wait times for each restaurant in the Memorial Union. Each card takes you to a dedicated page for the restaurant that allows users to filter a live menu of the restaurant’s selection by type, recommendations, and availability.</p>
        <p>Additional information like a complete list of a restaurant’s hours, their phone number, as well as a popular times chart, can be found by tapping the right pointing arrow at the header of the page.</p>"
        img="img/memorial-union/midfiFood.webp"
    />

    <p class="label">Social</p>
    <TextBlock
        textHTML="<p>The Social page is dedicated to all social activities at the MU such as events and games. We added a carousel for a quick view of upcoming MU events and added a “See More” button for users to view these events in a calendar view that was influenced by Google Calendar and Apple Calendar for the design and user flow. When a user clicks on a date, an hourly view of the selected date is displayed as a popup. When they click on an event, the popup switches to a detailed popup of that event. There, they are able to learn more about the event and add the event to their personal calendar if they choose to do so.</p>
        <p>The Social page also allows users to explore the Games Area, a recreational center with activities such as billiards, bowling, and gaming. They can view a popular times chart to avoid long wait times and click on a card component to learn more about different games.</p>"
        img="img/memorial-union/midfiSocial.webp"
    />

    <p class="label">Services</p>
    <TextBlock
        textHTML="<p>With the Services tab, we played around with different styles and layouts to find the best way to showcase the range of services at the MU and what each service does. We strived to include information such as hours and a description of each service.</p>"
        img="img/memorial-union/midfiServices.webp"
    />

    <h2>User Testing & High-fidelity Prototyping</h2>
    <TextBlock
        textHTML="<p>Following our mid-phase evaluation, we sought for feedback on our design and prototype by conducting usability tests.</p>
        <p>We conducted a series of 7 usability tests specifically targeting current UC Davis students. These tests encompassed four distinct sets of tasks: Study, Food, Social, and Services.</p>
        <p>These tests provided valuable insights into the pain points and strengths of our design and prototype. Through these tests, we found 3 main pain points.</p>"
        img="img/memorial-union/testingInsights.webp"
    />

    <p class="label">Booking study rooms</p>
    <TextBlock
        textHTML="<p>During the usability tests focused on the Study page, we identified a problem where users were mistakenly led to believe that they could book study rooms through the app. To address this, we implemented a helper tab that explicitly states that the rooms are only bookable for student organizations. This solution aims to prevent confusion and ensure that users have accurate expectations regarding the availability of study rooms.</p>"
        img="img/memorial-union/studyBeforeAfter.webp"
    />

    <p class="label">Checking restaurant wait times</p>
    <TextBlock
        textHTML="<p>During the usability tests focused on the Food page, we discovered that users were unaware of the popular times page when checking wait times for food. To address this, we added helper text to guide users to the popular times page and clarified that the app does not currently support ordering. These changes aim to improve user understanding and streamline the process of checking wait times for food.</p>"
        img="img/memorial-union/foodBeforeAfter.webp"
    />

    <p class="label">Viewing event listings</p>
    <TextBlock
        textHTML="<p>During the usability tests focused on Social page, we discovered that users wanted a more comprehensive view of all the events rather than just a calendar view. To address this, we implemented a list view along with a search bar, allowing users to quickly and efficiently browse through all the events at a glance. This solution aims to improve user experience and provide a convenient way for students to explore and engage with the various events happening at the MU.</p>"
        img="img/memorial-union/socialBeforeAfter.webp"
    />

    <h1>Design System</h1>
    <img src="img/memorial-union/designSystem.webp" alt="">

    <h1>Final Prototype</h1>
    <TextBlock
        textHTML="<p>The Map tab allows users to see a full map of the MU that highlights all of the services and amenities that the MU has to offer. Users are able to filter the map through 4 tags: Study, Food, Social, and Services. They can also click on a specific landmark on the map to find out more about it and be redirected to the main tab corresponding with that landmark.</p>"
        img="img/memorial-union/map.gif"
    />

    <TextBlock
        textHTML="<p>The Food tab features a complete list of all the food spots available at the MU with a live filterable menu that shows what items are currently in stock and the popular times of each restaurant so that students can plan their visit to the MU accordingly.</p>"
        img="img/memorial-union/food.gif"
    />

    <TextBlock
        textHTML="<p>The Study tab is designed to showcase all MU study spots, which include general seating in open public areas in addition to study rooms. Users can not only filter through these study spots by floor or occupancy but also find information about hours, seating availability, and study room availability all on one screen. They can also click into a study room to learn more about study room rules as well as the study room’s availability status during specific times. Besides study rooms, users can learn more about a certain study spot such as how busy it is and where it is located in the MU with the option to be redirected to the Map page.</p>"
        img="img/memorial-union/study.gif"
    />

    <TextBlock
        textHTML="<p>The Social tab is a centralized hub for all social activities such as MU events and games at the Games Area, a recreational center with activities such as billiards, bowling, and gaming. Users can view MU events in a Calendar and List view. They can click a card component to learn more about an event and add it to their personal calendar should they choose to do so. Also on the Social tab is a section dedicated to the Games Area. Here users can click on a card component to learn information such as prices and estimated wait times for the different games.</p>"
        img="img/memorial-union/social.gif"
    />

    <TextBlock
        textHTML="<p>Our final Services tab is dedicated to students who want to explore and delve deeper into the numerous services provided by the MU. From The Pantry ensuring no student goes hungry to Aggie Compass guiding students towards wellness and success, UC Davis’ Memorial Union has a range of services tailored to meet student needs. This is just some of the countless other services waiting to be discovered through our app, with each service designed to enhance the student experience at UC Davis.</p>"
        img="img/memorial-union/services.gif"
    />

    <h1>Challenges</h1>
    <p>When designing this app for UC Davis’ Memorial Union, we came across challenges such as:</p>
    <ul>
        <li>Difficulty with UX Copy and UX Writing to inform users about app features where we struggled to clearly showcase study room rules and the menu stock availability feature</li>
        <li>Providing context for users to easily navigate through the app while avoiding cognitive overload</li>
        <li>Creating an interactive map of the MU without sacrificing UI</li>
    </ul>

    <h1>Next steps</h1>    
    <ol>
        <li> <span class="emphasis">Conduct more user research on faculty and visitors.</span><br>Since our respondents are nearly all students, we are missing data on staff and visitors, which are some of the demographics that also utilize the MU. Thus, if we had more time, we would like to learn more about how they interact with the MU and expand the scope of the app to accommodate them and their needs.</li>
        <li> <span class="emphasis">Create a more dynamic map that tracks your location upon entering the MU</span><br>‍Currently, our map only tells users where services are located. However, if we expanded the scope of our app to include visitors, we would implement a dynamic map that provides directions from your current location. This will be especially helpful for visitors, freshmen, and transfer students who may not be familiar with the layout of the MU.</li>
        <li> <span class="emphasis">Give users the ability to order ahead in the CoHo through the app</span><br>‍During our user research, students shared that they wanted the ability to order ahead at the CoHo to skip the long lines. Due to our time constraint, however, we were unable to implement this feature into our final prototype. We would therefore like to expand our app to include this useful feature if given the opportunity.</li>
    </ol>






</section>



<Footer/>
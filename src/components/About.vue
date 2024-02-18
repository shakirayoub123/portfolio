<template>
  <div class="card" id="about">
    <div class="container">
      <div class="row">
        <div class="about-col-1">
          <img src="../assets/IMG_20230312_001125_915.jpg" alt="">
        </div>
        <div class="about-col-2">
          <h1 class="subtitle">About Me</h1>
          <p>I'm actively contributing as a Front-end Developer at <span class="red-letter">Ladybird Web Solution</span>
            in Jammu.
            Leveraging robust problem-solving abilities and years of expertise in crafting cutting-edge websites, I'm
            deeply driven and proficient. Holding a Bachelor's degree in Computer Science fuels my innovation and
            passion for pushing boundaries in web development.</p>
          <div class="tab-titles">
            <p class="tab-links active-link" @click="(event) => openTab('skills', event)">Skills</p>
            <p class="tab-links" @click="(event) => openTab('education', event)">Education</p>
            <p class="tab-links" @click="(event) => openTab('experience', event)">Experience</p>
            <p class="tab-links" @click="(event) => openTab('internship', event)">Internship</p>
          </div>
          <div class="tab-contents active-tab" id="skills">
            <ul>
              <div class="tab-content" :class="{ active: activeTab === 'skills' }">
                <h2>Skills</h2>
                <div class="skills-buttons">
                  <button class="skills-button" v-for="(language, index) in programmingLanguages" :key="index"
                          :style="{ backgroundColor: getRandomColor() }">
                    {{ language }}
                  </button>
                </div>
              </div>
              <div class="tools-list">
                <h2>Tools</h2>
                <div class="skills-buttons">
                  <button class="skills-button tool-button" v-for="(tool, index) in toolsList" :key="index"
                          :style="{ backgroundColor: getRandomColor() }">
                    {{ tool }}
                  </button>
                </div>
              </div>
            </ul>
          </div>

          <!-- education-->
          <div class="tab-contents" id="education">
            <div class="education-cards ">
              <div class="education-card" v-for="(education, index) in educationDetails" :key="index">
                <div class="heading">{{ education.heading }}</div>
                <div class="period "><span class="session">Session: </span>{{ education.period }}</div>
                <div class="details"><span class="session">Course: </span>{{ education.details }}</div>
              </div>
            </div>
          </div>

          <!--          experiance-->
          <div class="tab-contents" id="experience">
            <ul>
              <li>
                <h2 class="heading">Ladybird Web Solution</h2>
                <p class="text-data"> Embarked on a dynamic journey as an Intern at Ladybird web
                  solution, contributing to the innovation behind <span class="red-letter">Faveo</span> Help-desk.
                  Collaborated closely with software artisans, co-crafting solutions
                  that catered to diverse client needs.
                  Evolved into an Associate Developer post-internship, weaving my
                  code into the fabric of Faveo's development.</p>
              </li>
              <h2>Skills Learned in LWS</h2>
              <div class="skills-buttons mb-1">
                <button class="skills-button" v-for="(language, index) in programmingLanguages" :key="index"
                        :style="{ backgroundColor: getRandomColor() }">
                  {{ language }}
                </button>
              </div>
            </ul>
          </div>

          <!--          Internships-->
          <div class="tab-contents" id="internship">
            <ul>
              <h2>Yarikul Infotech Srinagar</h2>
              <li>
                <p class="text-data rounded" style="background-color: #4f4f4f; color: white; padding: 15px">
                  During my tenure at <span class="red-letter"> Yarikul Infotech Srinagar</span>,
                  I acquired expertise in HTML, CSS, JavaScript, and Bootstrap.
                  This hands-on experience significantly enhanced my skills, which I further applied to my college
                  projects,
                  demonstrating practical proficiency.
                </p>
              </li>
            </ul>
            <ul>
              <h2 class="text-data">Ladybird Web Solution pvt ltd</h2>
              <p class="text-data rounded" style="background-color: #4f4f4f; color: white; padding: 15px">
                I embarked on a fulfilling journey at <span class="red-letter">Ladybird Web Solution</span>,
                where I underwent a comprehensive three-month internship. During this period, I immersed myself in HTML,
                CSS, JavaScript, Bootstrap, Vue.js, Vuex, and Testutils, channeling these skills towards practical
                applications and gaining valuable hands-on experience.
              </p>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <!--    test-->
    <div class="heading mt-4">
      <h2 >Certificates</h2>
    </div>
    <div class="row cont">
      <div class="card cont1 bg-light">
        <div class="card  cont2 bg-light">
          <img style="height: 220px; object-fit: cover;" src="../assets/img.png" class="card-img-top" alt="Card image">
          <div class="card-body">
            <!--              <h2 class="card-title">HackerRank</h2>-->
            <p class="card-subtitle">Received the JavaScript Certificate from <span
                style="color: #1ba94c; font-weight: bold">HackerRank</span>, showcasing proficiency in fundamental and
              advanced concepts</p>
            <a target="_blank" href="https://drive.google.com/file/d/1oLGFxcEEtow_anB4z94NbeStxyYPl6ns/view?usp=sharing"
               class="footer">View</a>
          </div>
        </div>
      </div>
      <div class="card cont1 bg-light">
        <div class="card  cont2 bg-light">
          <img style="height: 220px; object-fit: cover;" src="../assets/img_1.png" class="card-img-top"
               alt="Card image">
          <div class="card-body">
            <p class="card-subtitle">Received the Problem Solving from <span style="color: #1ba94c; font-weight: bold">HackerRank</span>,
              showcasing proficiency in fundamental and advanced concepts</p>
            <a target="_blank" href="https://drive.google.com/file/d/1oLGFxcEEtow_anB4z94NbeStxyYPl6ns/view?usp=sharing"
               class="footer">View</a>
          </div>
        </div>
      </div>
      <div class="card cont1 bg-light">
        <div class="card  cont2 bg-light">
          <img style="height: 220px; object-fit: cover;" src="../assets/php-mysql.jpg" class="card-img-top"
               alt="Card image">
          <div class="card-body">
            <p class="card-text">Acknowledges successful completion of the PHP and MySQL test, conducted at MIET, utilizing course material from the <span style="color: #1ba94c; font-weight: bold">Spoken Tutorial, IIT Bombay.</span></p>
            <a target="_blank" href="https://drive.google.com/file/d/1oLGFxcEEtow_anB4z94NbeStxyYPl6ns/view?usp=sharing"
               class="footer">View</a>
          </div>
        </div>
      </div>
      <div class="card cont1 bg-light">
        <div class="card  cont2 bg-light">
          <img style="height: 220px; object-fit: cover;" src="../assets/react.png" class="card-img-top"
               alt="Card image">
          <div class="card-body">
            <p class="card-text">Earned React proficiency on <span
                style="color: #1ba94c; font-weight: bold">HackerRank</span>, showcasing expertise in crafting dynamic
              UIs, state management, and building innovative web apps.</p>
            <a target="_blank" href="https://drive.google.com/file/d/1oLGFxcEEtow_anB4z94NbeStxyYPl6ns/view?usp=sharing"
               class="footer">View</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
let tablinks = document.getElementsByClassName("tab-links")
let tabcontents = document.getElementsByClassName("tab-contents")
export default {
  name: 'About',
  data() {
    return {
      programmingLanguages: [
        'HTML', 'CSS', 'JavaScript', 'ReactJs', 'VueJs', 'Bootstrap', 'Rest Api', 'Redux', 'Vuex', 'PHP', 'Wordpress', 'NodeJs', 'Express',
      ],
      toolsList: [
        'Postman', 'IDE editors', 'Git', 'Netlify', 'Github', 'MySql', 'Xampp', 'Testutils',
      ],
      showTools: false,
      educationDetails: [
        {
          heading: 'MASAI SCHOOL',
          period: '2022 - 2023',
          details: 'MERN Stack',
        },
        {
          heading: 'MIET Jammu',
          period: '2016 - 2020',
          details: 'Bachelor of Engineering',
        },
        {
          heading: 'JKBOSE',
          period: '2014 - 2015',
          details: 'Intermediate (12th)',
        },
        {
          heading: 'JKBOSE',
          period: '2013 - 2014',
          details: 'Matriculation (10th)',
        },
      ],
    };
  },

  methods: {
    getRandomColor() {
      const letters = '0123456789ABCDEF';
      let color = '#';
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    },
    openTab(tabName, event) {
      for (let i = 0; i < tablinks.length; i++) {
        tablinks[i].classList.remove("active-link")
      }
      for (let i = 0; i < tabcontents.length; i++) {
        tabcontents[i].classList.remove("active-tab")
      }
      event.currentTarget.classList.add("active-link")
      document.getElementById(tabName).classList.add("active-tab")
    }
  },
}
</script>

<style scoped>
.heading h2{
  text-align: center;
  margin-bottom: 30px;
}
a{
 display: flex;
  justify-content: center;
  cursor: pointer;
  color: #0598da;
}
a:hover{
  color: #067bb7;
  transform: scale(1.1); /* Adjust the scale factor as desired */
  transition: transform 0.3s ease; /* Smooth transition effect */
}

.cont2{
  overflow: hidden;

}
.cont2 img{
  transform: translateY(0);
  transition: transform 0.3s ease-out, box-shadow 0.3s ease-out;
}
.cont2:hover img {
  transform: scale(1.1); /* Adjust the scale factor as desired */
  transition: transform 0.3s ease; /* Smooth transition effect */
}
.card-title {
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 5px;
}

.card-subtitle {
  font-size: 16px;
  color: #777;
  font-style: italic;
  margin-bottom: 15px;
}

.cont {
  display: grid;
  grid-template-columns: repeat(2, 37%);
  justify-content: center;
  gap: 20px; /* Adjust spacing between cards */
}

.cont1 {
  padding: 20px;
  transform: translateY(0);
  transition: transform 0.3s ease-out, box-shadow 0.3s ease-out;
}
 .cont1:hover{
   transform: translateY(-10px);
   box-shadow: -5px -5px 30px 5px red, 5px 5px 30px 5px blue;
   transition-delay: 0.2s;
}

.text-data {
  font-style: italic;
}

.red-letter {
  color: #ff004f;
}

.education-card:hover {
  background: #4f4f4f;
  transform: translateY(-10px);
  box-shadow: -5px -5px 30px 5px red, 5px 5px 30px 5px blue;
  transition-delay: 0.2s;
}

.period {
  font-style: italic;
}

.session {
  color: white;
  font-weight: bold;
}

.education-card .heading {
  color: white;
  font-weight: bold;
}

.education-cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.education-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background-color: #4f4f4f;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  flex-basis: calc(50% - 20px);
}

.card {
  background-color: #080808;
}

.subtitle {
  font-size: 36px;
  margin-bottom: 20px;
  position: relative;
}

/* New styles for the underline */
.subtitle::before {
  content: '';
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 40%; /* Adjust the width of the underline as needed */
  height: 2px;
  background-color: #ff004f; /* Your desired underline color */
}

.tool-button:hover {
  background-color: #d80045;
}

.skills-buttons {

  display: flex;
  flex-wrap: wrap;
  margin-top: 10px;
}

.skills-button {
  background-color: #ff004f;
  color: white;
  border: none;
  padding: 8px 15px;
  margin-right: 10px;
  margin-bottom: 10px;
  border-radius: 5px;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
}

.skills-button:hover {
  background-color: #d80045;
  transform: scale(1.05);
}

#about {
  padding: 80px 0;
  color: #ababab;
}

.about-col-1 {
  flex-basis: 35%;
}

.about-col-1 img {
  width: 100%;
  border-radius: 15px;
}

.about-col-2 {
  flex-basis: 60%;
}

.tab-titles {
  display: flex;
  margin: 20px 0 40px;
}

.tab-links {
  margin-right: 50px;
  font-size: 18px;
  font-weight: 500;
  cursor: pointer;
  position: relative;
}

.tab-links::after {
  content: '';
  width: 0;
  height: 3px;
  background: #ff004f;
  position: absolute;
  left: 0;
  bottom: -8px;
  transition: 0.5s;
}

.tab-links.active-link:after {
  width: 50%;
}

.tab-contents ul li {
  margin: 10px 0;
}

.tab-contents ul li span {
  color: #b54769;
  font-size: 14px;
}

.tab-contents {
  display: none;
}

.tab-contents.active-tab {
  display: block;
}

@media only screen and (max-width: 600px) {
  #about {
    padding: 50px 0 25px;
  }

  .subtitle {
    font-size: 40px;
  }

  .row {
    display: flex;
    flex-direction: column;
  }

  .about-col-1 {
    text-align: center;
    margin-bottom: 15px;
  }

  .about-col-1 img {
    width: 100%;
  }

  .about-col-2 {
    font-size: 15px;
  }
}</style>
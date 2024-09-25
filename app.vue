<template>
  <div>
    <header>
      <h1>{{ name }}</h1>
      <p>{{ title }} | {{ location }} | {{ contactInfo }}</p>
    </header>

    <div class="container">
      <div class="profile">
        <img :src="profilePicture" alt="Your Photo" />
        <div class="profile-info">
          <h2>{{ name }}</h2>
          <p>{{ jobTitle }}</p>
          <p>
            Email: <a :href="'mailto:' + email" class="link">{{ email }}</a> |
            Phone: <span class="phone">{{ phone }}</span>
          </p>
          <div class="button-container">
            <a :href="linkedinUrl" class="button">LinkedIn</a>
            <a :href="githubUrl" class="button">GitHub</a>
          </div>
        </div>
      </div>

      <div class="section">
        <h3>About Me</h3>
        <p>{{ aboutMe }}</p>
      </div>

      <div class="section">
        <h3>Experience</h3>
        <ul>
          <li v-for="experience in experiences" :key="experience.title">
            <span>{{ experience.title }} - {{ experience.company }}</span> ({{ experience.years }})
            <p>{{ experience.description }}</p>
          </li>
        </ul>
      </div>

      <div class="section">
        <h3>Education</h3>
        <ul>
          <li v-for="education in educations" :key="education.degree">
            <span>{{ education.degree }} - {{ education.school }}</span> ({{ education.years }})
            <p>{{ education.description }}</p>
          </li>
        </ul>
      </div>

      <div class="section">
        <h3>Skills</h3>
        <ul>
          <li v-for="skill in skills" :key="skill">{{ skill }}</li>
        </ul>
      </div>

      <div class="section">
        <h3>Projects</h3>
        <ul>
          <li v-for="project in projects" :key="project.name">
            <span>{{ project.name }}</span>
            <p>{{ project.description }}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Hello everyone! I'am Rohim",
      title: "Mahasiswa D3 Teknologi Informasi",
      location: "Jl. Terusan Ijen No.861 Malang",
      contactInfo: "Contact Information",
      profilePicture: "https://silamparitv.disway.id/upload/large/dab3f9742ff365ea2d36f5d803ef2c3d.jpg", // Ganti dengan URL gambar yang sesuai
      jobTitle: "Web Developer | Designer | Programmer",
      email: "abdurrohimsyah05@gmail.com",
      phone: "+62 859 2745 2798",
      linkedinUrl: "https://www.linkedin.com/in/abdur-rohim-syah-sjadja%E2%80%99ah-bb148a289?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app",
      githubUrl: "https://github.com/yourusername",
      aboutMe: "Perkenalkan nama saya Abdur Rohim Syah Sjadja'ah. Lahir pada tanggal 11 Februari 2005. Umur saya 19 tahun. Hobi saya workout dan bermain game. Saya adalah mahasiswa yang sedang menempuh pendidikan D3 Teknologi Informasi Fakultas Vokasi Universitas Brawijaya.",
      experiences: [
        { title: "Job Title", company: "Company Name", years: "Year - Year", description: "Describe your responsibilities and achievements in this role." },
        { title: "Job Title", company: "Company Name", years: "Year - Year", description: "Describe your responsibilities and achievements in this role." }
      ],
      educations: [
        { degree: "D3 Teknologi Informasi", school: "Universitas Brawijaya", years: "2023 - now", description: "Relevant coursework or achievements." }
      ],
      skills: ["HTML", "CSS", "PHP", "JavaScript", "Figma", "Nuxt.js", "MySQL"],
      projects: [
        { name: "Project Name", description: "No project yet." },
        { name: "Project Name", description: "No project yet." }
      ]
    };
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;600;800&display=swap');

body {
  font-family: 'Raleway', sans-serif;
  margin: 0;
  padding: 0;
  color: #333;
  line-height: 1.6;
  background-color: #f9f9f9;
}

header {
  background: linear-gradient(to right, #00b4db, #0083b0, #a020f0); /* Colorful and masculine gradient */
  color: #fff;
  padding: 40px 0;
  text-align: center;
  border-bottom: 8px solid #0083b0;
}

header h1 {
  margin: 0;
  font-size: 3.5em;
  font-weight: 800;
  letter-spacing: 2px;
}

.container {
  max-width: 1000px;
  margin: 30px auto;
  padding: 30px;
  background: #fff;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  border-radius: 15px;
  border: 2px solid #00b4db;
}

.profile {
  display: flex;
  gap: 30px;
  align-items: center;
  margin-bottom: 30px;
}

.profile img {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  border: 5px solid #00b4db;
  transition: transform 0.3s;
}

.profile img:hover {
  transform: scale(1.1);
}

.profile-info h2 {
  margin: 0;
  font-size: 2.8em;
  color: #333;
  font-weight: 600;
}

.profile-info p {
  margin: 5px 0;
  font-size: 1.4em;
  color: #555;
}

.button-container {
  margin-top: 20px;
}

.button {
  display: inline-block;
  padding: 12px 30px;
  font-size: 1em;
  font-weight: 600;
  color: #fff;
  background-color: #00b4db;
  border: none;
  border-radius: 50px;
  text-decoration: none;
  transition: background-color 0.3s, transform 0.2s;
  margin: 5px;
}

.button:hover {
  background-color: #0083b0;
  transform: translateY(-2px);
}

.section {
  margin-bottom: 30px;
}

.section h3 {
  font-size: 2.4em;
  font-weight: 600;
  color: #00b4db;
  margin-bottom: 20px;
}

.section ul {
  list-style: none;
  padding: 0;
}

.section li {
  margin-bottom: 20px;
  background: #f5f5f5;
  border-radius: 12px;
  padding: 20px;
  transition: background 0.3s;
}

.section li:hover {
  background: #e0f7fa;
}

.link {
  color: #00b4db;
}

.phone {
  color: #00b4db;
}

.section h3, .section li span {
  letter-spacing: 1px;
}

</style>

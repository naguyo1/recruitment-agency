<script>
  // @ts-nocheck

  const company = {
    name: "JEPHTHAH Recruitment Agency",
    description:
      "JEPHTHAH Recruitment Agency is a licensed recruitment and manpower outsourcing company dedicated to connecting skilled and semi-skilled workers with verified employment opportunities abroad. We work closely with trusted international employers to ensure safe, legal, and transparent recruitment processes.Founded with the goal of reducing unemployment and promoting ethical labor migration, our agency focuses on placing candidates in sectors such as construction, hospitality, healthcare support, manufacturing, and domestic services.",
    locations: ["Kampala", "Nairobi", "Dar es Salaam"],
    contact: {
      phone: "+256 708 317069",
      email: "jephthahrecruitment@gmail.com"
    }
  };

  const jobs = [
    {
      title: "House Maids",
      type: "Domestic",
      country: "Saudi Arabia",
      image: "/images/maids.jpg"
    },
    {
      title: "Nurse Professionals",
      type: "Medical",
      country: "Qatar",
      image: "/images/nurses.jpg"
    },
    {
      title: "Professional Teachers",
      type: "Education",
      country: "UAE",
      image: "/images/teachers.jpg"
    },
    {
      title: "Care Givers",
      type: "Health Care",
      country: "Canada",
      image: "/images/care takers.jpg"
    },
    {
      title: "Casual Workers",
      type: "General Labor",
      country: "Oman",
      image: "/images/casual workers.jpg"
    }
  ];
</script>


<main class="container">

  <header class="hero">
    <h1>{company.name}</h1>
    <h2>About Us:</h2>
    <p>{company.description}</p>
  </header>

  
 <section>
  <h2>Posted Jobs</h2>

  <div class="jobs-grid">
    {#each jobs as job}
      <div
        class="job-card"
        style="background-image: url('{job.image}')"
      >
        <div class="overlay">
          <h3>{job.title}</h3>
          <p class="meta">{job.type}</p>
          <span class="badge">{job.country}</span>
        </div>
      </div>
    {/each}
  </div>
</section>


  
  <section>
    <h2>Office Locations</h2>
    <ul class="locations">
      {#each company.locations as location}
        <li>{location}</li>
      {/each}
    </ul>
  </section>

  
  <section class="contact">
    <h2>Contact Information</h2>
    <p><strong>Phone:</strong> {company.contact.phone}</p>
    <p><strong>Email:</strong> {company.contact.email}</p>
  </section>
</main>

<style>
  :root {
    --primary: #dc2626;
    --secondary: #1f2937;
    --bg: #f9fafb;
    --card: #ffffff;
    --muted: #6b7280;
  }

  .container {
    max-width: 1100px;
    margin: auto;
    padding: 2rem 1rem;
    font-family: system-ui, sans-serif;
    background: var(--bg);
    color: var(--secondary);
  }

  .hero {
    text-align: center;
    margin-bottom: 3rem;
  }

  h1 {
    color: var(--primary);
    font-size: 2.5rem;
    margin-bottom: 0.5rem;
  }

  h2 {
    margin: 2rem 0 1rem;
    font-size: 1.5rem;
  }

  p {
    color: var(--muted);
  }

  
  .jobs-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.5rem;
}

.job-card {
  position: relative;
  height: 260px;
  border-radius: 14px;
  background-size: cover;
  background-position: center;
  overflow: hidden;
  cursor: pointer;
  box-shadow: 0 12px 25px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.job-card:hover {
  transform: translateY(-6px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.25);
}


.overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.7),
    rgba(0, 0, 0, 0.2)
  );
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  color: white;
  transform: translateY(30%);
  transition: transform 0.3s ease;
}

.job-card:hover .overlay {
  transform: translateY(0);
}

.overlay h3 {
  margin: 0;
  font-size: 1.3rem;
}

.meta {
  font-size: 0.9rem;
  opacity: 0.9;
}

.badge {
  align-self: flex-start;
  margin-top: 0.5rem;
  background: #dc2626;
  padding: 0.3rem 0.7rem;
  border-radius: 999px;
  font-size: 0.8rem;
}

  
  .locations {
    list-style: none;
    padding: 0;
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .locations li {
    background: var(--card);
    padding: 0.7rem 1.2rem;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
  }

  
  .contact {
    background: var(--card);
    padding: 2rem;
    border-radius: 12px;
    margin-top: 3rem;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.05);
  }
</style>


<script setup>
import { ref } from 'vue'
import '../assets/style.css'

const selectedWeek = ref(
  window.location.pathname === '/viikko2' ? '/viikko2' : '/'
)

function navigateToWeek() {
  if (selectedWeek.value) {
    window.location.href = selectedWeek.value
  }
}
</script>

<template>
  <div class="site">
    <header>
      <h1>My Linux Server</h1>
      <p>Building, configuring and understanding my own server.</p>

      <div class="week-row">
        <span class="week">WEEK 01 · LINUX BASICS</span>

        <nav class="week-nav" aria-label="Week navigation">
          <label for="week-select">Select week:</label>
          <select
            id="week-select"
            v-model="selectedWeek"
            @change="navigateToWeek"
          >
            <option value="/">Week 1</option>
            <option value="/viikko2">Week 2</option>
          </select>
        </nav>
      </div>
    </header>

    <main>
      <section>
        <h2><span>01 /</span> Linux distribution and version</h2>
        <p>AlmaLinux 10.</p>
      </section>

      <section>
        <h2>
          <span>02 /</span>
          What is Nginx, and what does it do on this server?
        </h2>

        <p>
          Nginx is a web server that can also be used as a reverse proxy.
          A proxy can be configured to cache previously requested content
          and serve it faster on subsequent requests.
        </p>

        <p>
          Nginx serves the web content on this server. It acts as a bridge
          between the website and the visitor's browser.
        </p>

        <p>
          Nginx is efficient at serving static content and handling many
          simultaneous connections. Apache is another widely used web
          server with its own strengths. Since I am more familiar with
          Apache, comparing the two gives me an opportunity to learn more.
        </p>
      </section>

      <section>
        <h2><span>03 /</span> Which commands did I use?</h2>

        <p>
          These commands were used to install Nginx, check its status
          and enable automatic startup.
        </p>

        <p>
          <strong><code>sudo dnf install nginx</code></strong><br />
          Installs Nginx from the configured AlmaLinux repositories
          using the DNF package manager.
        </p>

        <p>
          <strong><code>sudo systemctl status nginx</code></strong><br />
          Displays the current status of the Nginx service, including
          whether it is running or has failed.
        </p>

        <p>
          <strong><code>sudo systemctl enable nginx</code></strong><br />
          Configures Nginx to start automatically when the server boots.
        </p>
      </section>
    </main>

    <footer>
      <p>&copy; TVT26KMO Linux Server Project</p>
      <a
        href="https://github.com/tslts/linux-server-projects"
        target="_blank"
        rel="noopener noreferrer"
      >
        ↗ GitHub
      </a>
    </footer>
  </div>
</template>

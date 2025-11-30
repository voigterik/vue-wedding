<script setup></script>
<template>
  <section class="details">
    <div id="details" class="anchor"></div>
    <h2>Details</h2>
    <section class="location">
      <h3>
        <svg
          width="20"
          height="20"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"
            fill="currentColor"
          />
        </svg>
        <a href="https://maps.app.goo.gl/DYMBwykvZBaKfgmy6" target="blank" title="Location"
          >Some place</a
        >
      </h3>
      <p>Sicut malus movie horror.</p>
      <p>
        Zombies reversus ab inferno, nam malum cerebro. De carne animata corpora quaeritis. Summus
        sit​​, morbo vel maleficia?
      </p>
      <p>
        De Apocalypsi undead dictum mauris. Hi mortuis soulless creaturas, imo monstra adventus
        vultus comedat cerebella viventium.
      </p>
      <h3>Groomsmen &amp; Bridesmaids</h3>
      <div class="team">
        <div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Jean Sibelius</div>
          </div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Carl Gustaf Emil Mannerheim</div>
          </div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Kimi Räikkönen</div>
          </div>
        </div>
        <div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Frida Kahlo</div>
          </div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Salma Hayek</div>
          </div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Ellen Ochoa</div>
          </div>
          <div class="person">
            <img src="../assets/images/profile.png" alt="" class="profile" />
            <div>Thalia</div>
          </div>
        </div>
      </div>
      <h3>Dress code</h3>
      <p>
        De Apocalypsi undead dictum mauris. Hi mortuis soulless creaturas, imo monstra adventus
        vultus comedat cerebella viventium.
      </p>
      <h3>General guidelines</h3>
      <p>
        De Apocalypsi undead dictum mauris. Hi mortuis soulless creaturas, imo monstra adventus
        vultus comedat cerebella viventium.
      </p>
    </section>
  </section>
</template>

<style scoped>
.details {
  position: relative;
  padding: 2rem;
  text-align: center;
  background: var(--color-soft-beige);
}

h2 {
  margin-bottom: 3rem;
}

p {
  margin: 1rem 0 2rem 0;
}

p + h3 {
  margin-top: 4rem;
}

.team {
  max-width: 1200px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
  justify-self: center;
  margin: 3rem 0 0 0;
}

.person {
  margin-bottom: 3rem;
}

.profile {
  max-width: 100px;
  margin-bottom: 1rem;
  padding: 0.125rem;
  display: inline-block;
  border-radius: 50%;
  border: 1px solid var(--color-secondary);
  transition: filter 1s;
  filter: grayscale(100%);
}

.profile:hover {
  filter: grayscale(0);
}
</style>

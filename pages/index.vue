<script setup>
const contacts = [
  {
    icon: "material-symbols:mail",
    to: "mailto:thanadon.tkp@gmail.com",
    label: "thanadon.tkp@gmail.com",
    iconSize: "h-5 w-5",
  },
  {
    icon: "material-symbols:call-outline-rounded",
    to: "tel:0943652353",
    label: "094-365-2353",
    iconSize: "h-5 w-5",
  },
  {
    icon: "mdi:github",
    to: "https://github.com/thanadon-tkp",
    label: "thanadon-tkp",
    iconSize: "h-6 w-6",
  },
];
const listMenu = [
  {
    key: "about",
    label: "About",
  },
  {
    key: "experience",
    label: "Experience",
  },
  {
    key: "projects",
    label: "Projects",
  },
];
const listExperience = [
  {
    period: "August 2022 - Present",
    job: "Front End Developer",
    companyName: "T-DEV Co., Ltd.",
    companyLink: "https://www.facebook.com/tdevco/",
    description:
      "Developed internal web applications for the organization, including machine monitoring systems, admin dashboards, and payment gateways, while optimizing website performance through caching techniques and file size minimization. Collaborated seamlessly with Back-End developers to integrate features, contributed to the development of new functionalities for the company’s online platform, and worked closely with the team under project lead supervision. Regularly communicated project updates to ensure alignment and progress across all stakeholders.",
    technologies: [
      "JavaScript",
      "Vue.js",
      "Nuxt.js",
      "HTML",
      "CSS & SCSS",
      "Tailwind CSS",
      "Nuxt UI",
      "Docker",
      "Golang",
    ],
  },
  {
    period: "July 2021 - March 2022",
    job: "Internship",
    companyName: "Siam Retail Development Co., Ltd",
    companyLink: null,
    description:
      "Developed a web application to streamline ERP data preparation for internal use, utilizing C# and the .NET Framework for backend coding, Bootstrap 5 for responsive design, and SQL Server and Oracle for database management. Additionally, contributed to website design using Figma to create user-friendly interfaces.",
    technologies: [
      "C#",
      ".NET Framework",
      "Bootstrap 5",
      "HTML & CSS",
      "JavaScript",
      "SQL Server",
      "Oracle",
    ],
  },
  {
    period: "2018 - 2019",
    job: "Hardware,MII Camp 2 | Software,MII Camp 3",
    companyName: "Mahanakorn University of Technology",
    companyLink: null,
    description:
      "A volunteer camp for repairing computers in rural schools, involving teams specializing in hardware, software, and networking.",
    technologies: [],
  },
];

const about = ref(null);
const aboutIsVisible = useElementVisibility(about);
const experience = ref(null);
const experienceIsVisible = useElementVisibility(experience);
const projects = ref(null);
const projectsIsVisible = useElementVisibility(projects);

const menuActive = computed(() => {
  let menu = "";

  if (aboutIsVisible.value) {
    menu = "about";
  } else if (experienceIsVisible.value) {
    menu = "experience";
  } else if (projectsIsVisible.value) {
    menu = "projects";
  }

  return menu;
});
</script>

<template>
  <div
    class="lg:flex lg:justify-between lg:gap-2 px-6 py-12 md:px-12 md:py-16 lg:py-0"
  >
    <header
      class="lg:sticky lg:top-0 lg:flex lg:max-h-screen lg:w-[48%] lg:flex-col lg:justify-between lg:py-24"
    >
      <!-- title -->
      <div>
        <h1
          class="text-3xl font-bold tracking-tight text-slate-200 sm:text-5xl"
        >
          Thanadon Trakanpong
        </h1>
        <h2
          class="mt-3 text-lg font-medium tracking-tight text-slate-200 sm:text-xl"
        >
          Front End Developer
        </h2>
        <p class="mt-4 max-w-xs leading-normal">
          Passionate about creating user-friendly websites and building seamless
          user experiences.
        </p>
      </div>
      <!-- menu -->
      <div class="flex flex-col gap-4 max-lg:hidden w-fit">
        <a
          v-for="item in listMenu"
          :href="`#${item.key}`"
          class="uppercase flex items-center gap-4 hover:text-white duration-200"
          :class="[menuActive == item.key && 'text-white font-medium']"
        >
          <!-- line -->
          <div
            class="w-6 h-0.5 border bg-white duration-200"
            :class="{
              '!w-12': menuActive == item.key,
            }"
          ></div>
          <!-- label -->
          {{ item.label }}
        </a>
      </div>
      <!-- contact -->
      <div
        class="flex gap-x-4 w-fit flex-wrap gap-y-3 max-lg:flex-col max-lg:mt-4"
      >
        <UButton
          v-for="item in contacts"
          :padded="false"
          :icon="item.icon"
          :to="item.to"
          variant="link"
          color="gray"
          target="_blank"
          class="hover:text-white duration-300 outline-none"
          :label="item.label"
          :ui="{
            icon: {
              size: {
                sm: item.iconSize,
              },
            },
          }"
        />
      </div>
    </header>
    <main class="pt-10 lg:pt-24 lg:w-[52%] lg:py-24">
      <!-- about -->
      <section
        id="about"
        ref="about"
        class="mb-16 scroll-mt-16 md:mb-24 lg:scroll-mt-24"
      >
        <!-- title -->
        <div
          class="sticky top-0 z-20 -mx-6 mb-4 w-screen px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
        >
          <h2
            class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
          >
            About
          </h2>
        </div>
        <p class="mb-4">
          A motivated Front-End Developer with a strong passion for creating
          user-friendly and efficient web applications. I continuously expand my
          skills and stay updated with the latest technologies to deliver
          high-quality solutions. My ability to learn quickly and adapt to new
          challenges enables me to tackle complex problems effectively.
        </p>
        <p class="mb-4">
          With a clear career path toward becoming a Full-Stack Developer, I am
          eager to take on new responsibilities and contribute to team success.
          I excel in collaborative environments, easily building rapport with
          colleagues, and bringing a proactive approach to every task. Ready to
          hit the ground running and deliver impactful results from day one.
        </p>
      </section>
      <!-- experience -->
      <section
        id="experience"
        ref="experience"
        class="mb-16 scroll-mt-16 md:mb-24 lg:scroll-mt-24"
      >
        <!-- title -->
        <div
          class="sticky top-0 z-20 -mx-6 mb-4 w-screen px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
        >
          <h2
            class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
          >
            Experience
          </h2>
        </div>
        <!-- list experience -->
        <ul>
          <li
            v-for="item in listExperience"
            class="grid grid-cols-1 lg:grid-cols-[minmax(10.5rem,auto)_1fr] gap-2 mb-12"
          >
            <!-- period -->
            <h2
              class="mt-1 text-xs font-semibold uppercase tracking-wide text-slate-500"
            >
              {{ item.period }}
            </h2>
            <!-- details -->
            <div>
              <NuxtLink
                :to="item.companyLink"
                target="_blank"
                class="font-medium leading-3 text-slate-200 hover:text-violet-300 focus-visible:text-violet-300 text-base"
              >
                <span>
                  {{ item.job }} ·
                  <span class="inline-block"> {{ item.companyName }}</span>
                  <UIcon
                    v-if="item.companyLink"
                    name="line-md:external-link"
                    class="ml-1 -mb-1"
                  />
                </span>
              </NuxtLink>
              <!-- description -->
              <p class="mt-2 text-sm leading-normal">
                {{ item.description }}
              </p>
              <!-- technologies -->
              <ul class="mt-2 flex gap-2 flex-wrap">
                <li
                  v-for="technologie in item.technologies"
                  class="flex items-center rounded-full bg-violet-400/10 px-3 py-1 text-xs font-medium leading-5 text-violet-300"
                >
                  {{ technologie }}
                </li>
              </ul>
            </div>
          </li>
        </ul>
      </section>
      <!-- projects -->
      <section
        id="projects"
        ref="projects"
        class="mb-16 scroll-mt-16 md:mb-24 lg:scroll-mt-24"
      >
        <!-- title -->
        <div
          class="sticky top-0 z-20 -mx-6 mb-4 w-screen px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
        >
          <h2
            class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
          >
            Projects
          </h2>
        </div>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis
          cupiditate quo quis molestias doloremque distinctio magni repudiandae
          illo explicabo veniam rerum quos, beatae, placeat optio assumenda
          debitis eveniet unde neque. Veniam beatae, alias optio rem obcaecati
          quaerat asperiores dolorem nostrum illo sed repudiandae sit sint.
          Eligendi commodi voluptatibus veritatis. Adipisci eveniet perspiciatis
          a dolor omnis consequuntur nesciunt odit facere dolore voluptates
          delectus, eaque suscipit tenetur cupiditate quod accusamus ad labore,
          in consequatur praesentium necessitatibus quas atque tempora
          reiciendis? Sapiente, beatae quo eius mollitia sed nihil dolorum dicta
          hic sunt alias, asperiores assumenda cum inventore totam voluptatum
          vel rem ipsa vero! Libero impedit vel at autem natus saepe minus,
          assumenda deleniti nisi quisquam. Aperiam ex fugiat soluta blanditiis
          earum ad. Quod aliquam nihil eligendi corrupti eos vel veritatis in ut
          maxime repudiandae minus autem hic tempore, molestiae earum similique
          at architecto illo sapiente explicabo! Ipsum ea, sunt consectetur fuga
          quidem cum commodi praesentium fugit eum odio hic obcaecati quia
          exercitationem eveniet rem earum ab corporis inventore amet? Velit
          accusantium soluta alias quia recusandae possimus rerum quasi
          voluptates at repellendus suscipit quos vero, voluptate neque? Cumque,
          rerum deserunt labore quisquam dignissimos eius facere assumenda illum
          modi iste voluptates id autem accusantium laborum, repellat itaque
          asperiores error voluptate ut perferendis debitis? Consequatur totam
          laudantium repellat sequi error voluptas quaerat accusantium modi
          saepe vel quia id qui, tempora minus mollitia nulla voluptate fugit
          quis commodi maiores aliquam. Id minus dolorem nam sequi repellat
          necessitatibus aliquid ea, ipsa dolorum? Perspiciatis dolores iure quo
          vitae omnis ipsa architecto, impedit tempore iusto adipisci
          perferendis accusamus minima voluptate ut. Inventore possimus porro
          eos nisi ipsam vitae deserunt quo enim pariatur doloremque. Aliquam
          odit illo repellendus facilis, autem animi non doloremque sed dolorum
          ea, sequi in excepturi magnam repellat. A ea officiis accusantium
          debitis vitae dolorem neque sint odit?
        </p>
      </section>
    </main>
  </div>
</template>

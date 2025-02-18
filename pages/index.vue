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
      "Git",
      "Docker",
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
const { width } = useWindowSize();

const playVideo = (value) => {
  const video = value.target.getElementsByTagName("video")[0];
  video.play();
};
const pauseVideo = (value) => {
  const video = value.target.getElementsByTagName("video")[0];
  video.pause();
};

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
const listProjects = computed(() => {
  if (width.value < 640) {
    return [
      [
        {
          type: "image",
          src: "/im-control-desktop.jpeg",
          text: ["Web monitor & control", "(Laundry)"],
        },
        {
          type: "image",
          src: "/washpay-1.jpeg",
          text: ["Home App"],
        },
        {
          type: "image",
          src: "/im-control-desktop-3.jpeg",
          text: ["Manage Branches"],
        },
        {
          type: "image",
          src: "/im-control-desktop-2.jpeg",
          text: ["Dashboard"],
        },
      ],
      [
        {
          type: "image",
          src: "/otteri-2.jpeg",
          text: ["Web Admin"],
        },
        {
          type: "image",
          src: "/qr-box-1.jpeg",
          text: ["QR Box", "monitor & control"],
        },
        {
          type: "image",
          src: "/qr-box-4.jpeg",
          text: ["QR Box", "summary"],
        },
        {
          type: "image",
          src: "/qr-box-3.jpeg",
          text: ["Control machine"],
        },
      ],
    ];
  }
  return [
    [
      {
        type: "image",
        src: "/im-control-desktop.jpeg",
        text: ["Web monitor & control", "(Laundry)"],
      },
      {
        type: "image",
        src: "/washpay-1.jpeg",
        text: ["Home App"],
      },
    ],
    [
      {
        type: "image",
        src: "/washpay-2.jpeg",
        text: ["Order the machine, pay"],
      },
      {
        type: "image",
        src: "/im-control-desktop-3.jpeg",
        text: ["Manage Branches"],
      },
      {
        type: "image",
        src: "/im-control-desktop-2.jpeg",
        text: ["Dashboard"],
      },
    ],
    [
      {
        type: "image",
        src: "/otteri-2.jpeg",
        text: ["Web Admin"],
      },
      {
        type: "image",
        src: "/qr-box-1.jpeg",
        text: ["QR Box", "monitor & control"],
      },
      {
        type: "image",
        src: "/qr-box-4.jpeg",
        text: ["QR Box", "summary"],
      },
      {
        type: "image",
        src: "/qr-box-3.jpeg",
        text: ["Control machine"],
      },
    ],
  ];
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
          class="hover:text-white duration-300 outline-none flex items-center gap-1"
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
        class="mb-16 scroll-mt-16 md:mb-24 lg:mb-32 lg:scroll-mt-24"
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
        class="mb-16 scroll-mt-16 md:mb-24 lg:mb-32 lg:scroll-mt-24"
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
        class="relative mb-16 scroll-mt-16 md:mb-24 lg:mb-32 lg:scroll-mt-24"
      >
        <!-- particles -->
        <Particles :accelerate="true" class="absolute -top-10 -z-10" />
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
        <div class="grid grid-cols-2 sm:grid-cols-3 gap-3">
          <div class="flex gap-3 flex-col" v-for="project in listProjects">
            <template v-for="file in project">
              <div
                v-if="file.type == 'image'"
                class="relative hover:scale-110 hover:z-10 duration-150"
              >
                <img :src="file.src" :class="file.class" />
                <div
                  class="absolute hover:opacity-0 duration-200 flex flex-col justify-center items-center top-0 left-0 w-full h-full bg-black/50 text-white font-semibold"
                >
                  <small
                    v-for="text in file.text || []"
                    class="text-center text-xs/4"
                  >
                    {{ text }}
                  </small>
                </div>
              </div>
              <div
                v-else-if="file.type == 'video'"
                class="relative"
                @mouseenter="playVideo"
                @mouseleave="pauseVideo"
              >
                <video muted loop>
                  <source :src="file.src" type="video/mp4" />
                </video>
                <div
                  class="absolute hover:opacity-0 duration-200 flex justify-center items-center top-0 left-0 w-full h-full bg-black/50 text-white font-semibold"
                >
                  <span class="max-sm:hidden">Hover me!</span>
                  <span class="sm:hidden">Click me!</span>
                </div>
              </div>
            </template>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

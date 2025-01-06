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
    class="lg:flex lg:justify-between lg:gap-4 px-6 py-12 md:px-12 md:py-16 lg:py-0"
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
        class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24"
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
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Obcaecati
          corrupti odio perferendis minima, consectetur distinctio nihil laborum
          quod officia, tempore eum, voluptatum harum est ea maiores maxime.
          Perferendis blanditiis aspernatur officia aliquam vel sit ipsam ut,
          expedita possimus dolore, quia impedit hic nesciunt perspiciatis.
          Maxime necessitatibus inventore at aliquam pariatur!
        </p>
      </section>
      <!-- experience -->
      <section
        id="experience"
        ref="experience"
        class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24"
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
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequatur
          autem id placeat molestias dolorum. Alias illum magnam tempore!
          Debitis modi doloribus hic, voluptas explicabo ut, temporibus
          molestiae a, quis cumque molestias! A asperiores eius sunt doloremque
          aspernatur porro tempore nemo ducimus commodi ipsam. Laudantium
          obcaecati at suscipit, necessitatibus sed explicabo ex unde minima
          libero officia id. Laboriosam quo consequatur optio eligendi laborum
          maiores adipisci porro cupiditate odit amet corporis, earum deleniti
          incidunt aut. Dolorum iusto laudantium deleniti velit minus nostrum
          numquam ab! Natus numquam sint qui in placeat corporis ducimus ex,
          veniam illo assumenda modi, aspernatur quae, adipisci saepe quas aut
          officiis consectetur totam sequi praesentium eveniet beatae.
          Consequuntur magnam ipsa fugiat quis tenetur, reprehenderit quia
          ratione harum accusamus corrupti officiis maxime molestiae adipisci
          enim magni nobis debitis voluptatibus fuga beatae, atque aperiam modi?
          Quo aliquid doloremque mollitia itaque animi molestiae rem distinctio
          quidem. Similique tenetur minus rem quae aliquid.
        </p>
      </section>
      <!-- projects -->
      <section
        id="projects"
        ref="projects"
        class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24"
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

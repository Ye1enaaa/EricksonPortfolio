<template>
  <div class="">
    <profile-component
      name="Erickson"
      profession="Fullstack Web Developer"
      description="I'm an Aspiring Software Engineer with one year of experience specializing"
      specialization="backend and internet of things development."
      resumeLink="online resume"
      avatarUrl="https://scontent.fmnl4-1.fna.fbcdn.net/v/t39.30808-6/428638466_3292971684336985_950038273816050461_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeHVTjetQMV5ml2-9GwBC2VdvOC7nXVYo8i84LuddVijyBk9ZyIeBVLNcS7ypVFY5k31-kuyTbZoQGskie4SfNCR&_nc_ohc=L312sKcVwh4AX846E7a&_nc_ht=scontent.fmnl4-1.fna&oh=00_AfC_UG5EILArrC9pe8c0bDZZnT3EfvxF8JuLjkdxpIWTxw&oe=65F4B924"
    />
    <more-details />
    <tech-stack-card-label roles="Frontend Development Tech Stack:" />
    <div class="flex justify-center">
      <tech-stacks-card
        class="q-ml-lg"
        v-for="(techStack, index) in techStackList"
        :key="index"
        :image="techStack.image"
        :tech="techStack.tech"
      />
    </div>
    <tech-stack-card-label roles="Backend Development Tech Stack:" />
    <div class="flex justify-center">
      <tech-stacks-card
        class="q-ml-lg"
        v-for="(techStack, index) in backendTechStackList"
        :key="index"
        :image="techStack.image"
        :tech="techStack.tech"
      />
    </div>
    <tech-stack-card-label roles="IoT and Database:" />
    <div class="flex justify-center">
      <tech-stacks-card
        class="q-ml-lg"
        v-for="(techStack, index) in ioTTechStackList"
        :key="index"
        :image="techStack.image"
        :tech="techStack.tech"
      />
    </div>
    <tech-stack-card-label roles="Tools:" />
    <div class="flex justify-center">
      <tech-stacks-card
        class="q-ml-lg"
        v-for="(techStack, index) in toolsList"
        :key="index"
        :image="techStack.image"
        :tech="techStack.tech"
      />
    </div>
    <div class="q-pa-lg"></div>
  </div>
</template>

<style scoped></style>
<script>
import MoreDetails from "src/components/MoreDetails.vue";
import ProfileComponent from "src/components/ProfileComponent.vue";
import TechStackCardLabel from "src/components/TechStackCardLabel.vue";
import TechStacksCard from "src/components/TechStacksCard.vue";
import { defineComponent } from "vue";

const techStackList = [
  {
    image: "https://www.computerhope.com/jargon/j/javascript.png",
    tech: "JavaScript",
  },
  {
    image:
      "https://cdn.freebiesupply.com/logos/large/2x/react-1-logo-png-transparent.png",
    tech: "ReactJS",
  },
  {
    image:
      "https://i.pinimg.com/736x/c5/5f/50/c55f50cb7be3c17582cc0e28f961fe56.jpg",
    tech: "VueJS",
  },
  {
    image:
      "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAw1BMVEUFChQAtP////8FAAAAAAAAuP8Atv8AvP8Auv8FAw0FBhADhLsFAAYFAAkCl9YAvf8BnuADc6QEUXQFN1C6ursFDhkFHCsDapgFIDEBq/ICicMCjsoDeq4Bp+0AAA8DcJ8EXIQFL0UESWkEQ2AEVHkFEyAFJzuOj5EFNEx2d3lXWVzDw8SvsLEEY41HSEzr7OxkZWgdICYsLjPy8vLY2NlRUlabnJ48PkJ/gILg4OEzNTkVGCB+foFtbnCnp6lfYWMAzv/ODFROAAARX0lEQVR4nO1da0PiOhMuJG3aAqWAyP0ieBd1V11d19V9//+vetsCzeRWegXk8Hw6x6VtnmQyM5lMJpp2xBFHJAJCu25BwUD3/cIo7knnFdcM1B/tB8XCgJrTg2CIAtjyf9p2Y4oAmjk+NCnFgwCaEl3X68Uz3JlAoKlZKpWIXTRDNHJ2RHFrDM9nO2NIDMM4aCltup6icQ9Y00RZiyOOOOKII4444jvgMNZ3ESgsCoH2peuKikKg6WSyLxQLGkKH1A/bkUVO/cAZ1lqzWW3XjSgWtZzE37aqCKJqHY5kWEtK3VZzet9p+OjcT5ut7vLP1q6blw12QK056bs9kxDTg+7D/w/vf3tuf9LsFrAm35bi8KVy1nBKxKNlGCURhuGRJSWnMfOlNr8Po97FFih6bW41XG/MpNw4nqbpNlo5uhbFj6GnneaVEtE3kQM0dVKqzBH6Fmrbm3tnw0T0KMnh2f7HyTx+Uzc5vZCkO91vjhZqN0pmOnorkmap0d5bE2Kh04qZcvjgQJqV073kaKOLCtE3NX+JDb/SSeVi/2QVoaGp5BdYBEK8Duj58Cj49j/CkujmcF/WpStU0bRkKoTOs+o9p9I5n3epZ1rtzs87FacXeAPS58zSNE8vICNsdOYSqdfiWQBnMtMEX3vth2uziaOwLAZxz/ZFVD0BlfEzTOJOWtFuZ+C4tiYukSlgg+yJqKJWTxRQj55zb8VzN73htO4dGUmz19o9RQs1xAHUyajTTmK6vbFsd0aiKjZIY9eGA7VdYQB1Mpgn90w8kvOByNF02zsdRjQ3+DYFBjtdo1DgMvDvM+Y7pIg6vIR6hkzLIFcW0gSzapDOrijaqE/4xvSzOiOea9Tnu430d2M2aoibgoEFU42fjThUVY22ROtqurtYOaJ2jxUnXeWFBOQu5tNJpe847sh1nP5wMp3bSlPpe0jcu3vb1zeoyzbCqA8U+gVdnA/9aI0fhVo63kEwinjuzrBpK55Bg7rBdl93yxTRZYltgdFUzBVUqSt8bN8frw/lDbdRk9XSRulyqxR5ghFWC1WillR6RfkcZ2m3S9ETUUgw0vNIy1DwlowtCmqtzRLUoxL1UjP082F1lmJ7SxrVRowW1XuR4pOBoTcZuC9tyS4il/nsqBYpPFkYaqg2Yr7lbkVOUR9qANPZ4KRlYuhNRof5WnHHMUCLO9BVMwebBCcbQ29KDCDFLfioaJ6MYFaGAsWiVxpWGxpvj+DGJyIZeq56jDdAiobRLnZJzGgZ3Ymh2yIYGqYxvNxsAGzkwI8Wq21QA3SnPoqjvJUMDdK7j7fbZCOoUc1GgRRRC0xCo1eLIy8KhgYZnccOdVi1HpgbpLjwlGfq6YcMPZ6fKGW45Bf/y+gSeDfGJsNfS72aREMgoyTmmQoZQz+gnWwc0AxIj6lYkKxQu9av01GsnsGvMLMBq+Ki3jJXYKh7z64fHmOMld+D/8JoAHIWFYe1LyuX6fQtcqmksBoNLx7wWPYthO75aKNBnNNQyiz8/HiFpc+O8cMJQxFocSNan9opY2FoSoeQtUr4pFy+GwtjYaP20OAj2XrpnH5/jB/LHhYfIkds+S8F72QsMUmfp6ieHjYCS6Z6E/wOf/nNLL9y8oaqQ3G/lDCxDvxeXmJhsc9i/Br8HY4iatZpD5fSrjJQR6k/oJrRoS+Dr1bNfP7EdGCrqKOLQXp9CluG78ohrkD/WPjHc/hn0IIBfeEGZRPBsKd60rqgBJkexLe0mS9/1g1C1yNxp8UcMav0sGsCPD6snh3jPy/0zz8oRUaKzIuUzptSSqFKhLPA+gmbWf4IJpR0u8YP7EIljn+VWXwFsxHjBfPXJ8oEaoLNLntCWKdAzUBNttQVIYIeRxfidk0QnIdzZ4zLPN4/PNtxxf3xEcop0ObkNF8PnBlCYI24Dg+ag+Yl0cgbJjfD8UtZxMOvR+FvQNtAi5zzINptoGbAggf/Y1vzEjB0JASNa47gjYSgHGAqoj5QNu08gzaoAd4M5jgvaYEBQ/eCjArBzrEVm6An+qG1hPpOz3ONAbWYDrStb+oZLHyG9gURCPKhTmgoNgLIKRrq9KU5Rt6WR6RXQ0gP2eIHvi2vS03jsorUMASCwpOR+BVStDXQkhwPYIAmwwmOBbWwNNCcmBr6Gd+U0JmJB6BPgcrb4J0mQQ2oMKCkJcrib9AUu8owFINH+DMRwfV7fUCzRc7yioED4Yf+Gn4WWnKzbAlUeSVyL3S1OPgb8AwGkfpuelrXTWRI9QwYD8E2e/hctqQKoh2maLfGbydfr6+vX4u7l7hUqX8KwpmersmJIHjnKHIIQ9NFJ650svjr3jU+/l2dbOYJB3Ek6+9sDOnkNmnIWWqy/60ZnpO1ljndMFcCtuPPE0l/QdzQQeyEszwvvwYKKfUjpOowdD/WHU3OY7XBp/n2GjWU79RgtPMWUzCpDFqzpCq1aJ8hw+Ug6gmKnFgYPyxkL13iIXSGkUN7vJVHhibw2EyqFgV3hpclfyYaerIQvEfyt8pSUscGmNt8PDdg7glNERXXPj5+02a06kyPxAXGt7JFR3m1MPNhW1So8jD6NjIl71MsDa6YZYCR6uSuJ6xSjpx8rKQqB98UzahM0AOzCs/5C8QcLKOeshBPFf+SyCoNvKEJnTc51PoB0xDMa7mQsrGxafrD1xjfiNYjfDfQfXlMRKq5gG5WrV9fmBhuysjz8gurGCXAJx3E0H4ZOVSkom8Dql/FEAZVPNWY6cP46V3JMIwi5GARrS6VCHBuPQhJS6DchEjzacbzPQFBdTARSTdrQAo1Q0XDzOoxfpNZrg/ZFkRq4Ke1m/P+BgP/QPuZzayDCLuLLaFlybTBvw2D6LtnCTrBWs7G5xt2c8vWpIKVDnSpZ/SEhexqdwHgKoqh57L8vP1x+xPj+JLlR/P4HRE/Nh8qh8wZNmAdJFFb+IOziydqhp5crxYQzydvsoEECcRwY+vpSXwnUPCZvRrQW7Klypgzzo9KhphxEu4s4YfVzmToY3J/Pu+CsmtjWWdU1JKVEMBnM+XpSJ6zHEeZ4jdOnh8EyavU9fVhdqKPBpOZOpMBrBGz+m3AWJiqpR6GDs6nnKJAUKTIbC0FZ95MZToLOg8ZZjUXwEEic8VazIKtX0gZSrZhymWLEz/U5CPJdVXGQZUGVrIuEYE5VHYW4+DIJ6LUUb8T5JSLJKvFBopWRoMIot1EdUKCDbr9lCgGS5RRH29cl8EQXdTU9yOylGHGyDdcT6vexO6wySyiPCAgmhZ+10odEEWyuEMqUKWl9nFZEXyXMZQH0p75n/KDqDbnVCspxzkm6OpQbXi4SfYkTNfxTylBiURzM1FXZncCM51xhRiLIRt0+BIGESYzMLgVxJRVp+rV304ZCrIn7BSH+CH8FOYG7i1D0ejHH0Nms3mPGHLGTtA18echs3m2pXmYWJeW4Zbt+hcxdanG6Zqt6NLE9rDMxaOkv1hCttQCPvWW7GEcn0ZYB/ODaP2RMuR9muCnUEy34tMk9UsDCDMxnl+6/CLdHtyKXxprbSFuQ91wjZeuLeQBG7Clrt6oz3FtEWd9KNuWFwZR9L3f5CtJEEfzVreKT+a4Pty8xg/aj/+93jE0BSUiUFQQhF/09KUi4z3HNf6mOI216sBgS/7p9ubq9WuxWHy9Xgmiw8Vp1AnscCIaZNSSJW3nGKeJjrXZqAvz1WACgvimjbE2ofVLjgNJEYPoWFuykw5R8VKEGmaSqhXx4qV84h88vBD+JipeipqJTKQ65l1F5z2zZNSHSU6oxIh5ozmf2mj2zlGCmLfVmifJlVLtW9DKSVz2dmaAXAsqqmxFpQ37FlaiZDDF3hOyK2Emt+Fp2TwPWaOSwVP0OFZA+YVc957k+4eoyRw1IO5lNp3NCK4Qclt+Xaf2ONf9Q/keMHPQqpS5aNWYMY7wXAXsRsAw3z1g6T4+4itd+Nog/bb9429AUXFiUQ/FJO99fGkuhtjPnjZopawhh3+Uy0BQ2XV++HG6Gs45F0OeTwNULODotFKNo+/XgoUGs0SkQgKENN98GkVOlEzhlXTipKjytYyZ05gNzCqn3UeFNO+cKEVem/p47zRh2eOxFrhydMNDJh/QK06f16Zai0lzE2HuN8vRLFWuk1QEXofqwjWllCHUcmlzEy9Uvo48v1RutZYCRUaNs7hluvHf1XIjjEvBFWL4TiqOqfNL7a4qdCfPEQ7TgBUke5WmFqMaOTj7th5E0TFljWHqHGFFUSpNlefNhqclJE0y6nfmF/IEhDVAfOBRzRCuawrI81bk6ktVnsDSJKWR0x8OG5NJo3ImUGT23VbqVDIPoYorIFdfdd5iwyCG7QjKl/kZCOJynM1yuFMxZIawiPMWijMzkTNRAiIsdPgNjeXOvigcYBYWc2ZGde5JrU5lEK2zEJ2SHpviZn8h555UZ9eEffdI1HnbhZ/4AOMykgzcTuHJos6uqc4fRtcPYiEEVESCq9RGGBMOmECxKej8oeoMqS31TqUwjBrbHizbywjElDkXxjIp7Ayp8hwwmtdLPAxp5Xm+zoP8jOXqHDHzfB0YveLOASvPcqOKUNhjNL8Wz3Lze53+klCCwCLCkDBbPaHAs9zq8/hsczxq957vIpRP5ueM7GRfcB4/eCUTEYYJ/0Wex1fWVKidApnUV+EaoaYCW/jIkp/W+FoGiu2LOqjTYoCzb4XWVFDXxaBBKW+NH4bc2LoYbB05mr0NEdbF0KqXTtg/0PPMpy6GGsraJqsifIbZm4FVYRV1whKrTC3Acbhc4rQoDWPU0Ky37J86jM/nUtskAur6NGhI/HBmh4vRBPdB+I8w9YiwVEIXVcw9G9R+IZBHPvVpoqCuMYQGhFTECpirGkOwrJslPYqy0MS9DFSrEKYgX141hqKgrhOFKtfSPvXrRI161VB28U/xVNq7ok6Uja4ZSUxQJyo1Imp9KWNPNlj3So4y+ZvF6lpfzBfi1/rKgFT12tbgMt4pw3ifTlCvLQNS1dxbQnrcLj7DZDX3gifS3RuVpm6iD4z/qs5px2KYvG6iZ1nS3b2Zovalv7d9pT5sH4dhitqXaGCmvF00ef1S60/EEfRYDNPUL0VDN17/i+1NXIN2Q62dGAxT1aBNf29k4jrCijz92Ay3XUdYS1wLOiPD7deC1pLW887GcBf1vLWENdkzMdxNTfaEdfWzMNxVXf1kdyNkYLizuxG0RPdbpGZY8P0WG96V4I6StAwLvqMEkYQU1ffMKPL015CfyNzCPTMb3xb/riBsfX69SB3Tl8XNhyIVevd3BWkJ7nsKEmutX39fF3cvL+/v7y8vd4vX37dtrMrE3I/7nhLf2VXFHFRppntzZ9d/4N41TTv4u/M07fDvPxStVtCmQ7rD8j9wD6mmHfxdspp2+PcB/wfudNYO/15uH4d+t7oWOCMVURkKVANs+JVOKlldo2JgBQY7SSKYtBMCl2H3JkIOC7UbJZlajM/PLDXae8vPh6f+p65cOcYZPuJOU8eqKQqewR7Hs6HCAmygVxqe5cBPQ80caESj5rmYlUQkfXqVeZIM/wigQb75YIqveK5Kw420CGtyviVxG77zk9vHt6SHffs+a/i3OevKG489b6DkNGYo4SGU/UHgdnabk77bM30bH9xcHZSc8/+35/YnzW6MEwv7DmvpqHVbzel9p+Gjcz9ttrrKAwpFopbjZOCw9rVDz9TaxcDVWqS4RI69QLVVJ3vPMJOU1c5cd5dxrThATqaTvwXOw7yAzuPdtvCNsfdjcMQRRxxxxBFHfE8cvJOBhumvk/keQOeZb5jYdxy8lO4DEDqAeFYU0MwZDAZO7XApoinRdb2uqpG7/tU3nk3LgggkWkwTVlPcL8Rj2N+NVbNzuaFxSgzD2E8ptU8TlalUADVdx3HcvdQ06P5/uZQj219rYZ+29nlHOw/YO8mMPeKb4f9YnjZSKahc2gAAAABJRU5ErkJggg==",
    tech: "Quasar",
  },
  {
    image:
      "https://media.dev.to/cdn-cgi/image/width=1080,height=1080,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fdxy1c2bvl6odeo52dodk.jpg",
    tech: "Tailwind",
  },
];

const backendTechStackList = [
  {
    image: "https://cdn.buttercms.com/w8lc0UqsQCnPG0Ax6aiM",
    tech: "Flask",
  },
  {
    image:
      "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Laravel.svg/1200px-Laravel.svg.png",
    tech: "Laravel",
  },
  {
    image:
      "https://adware-technologies.s3.amazonaws.com/uploads/technology/thumbnail/20/express-js.png",
    tech: "ExpressJS",
  },
  {
    image:
      "https://pbs.twimg.com/profile_images/1235868806079057921/fTL08u_H_400x400.png",
    tech: "Spring Boot",
  },
];

const ioTTechStackList = [
  {
    image:
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzVHI7cAcF3suzW1qfzDZNHPKo21e-Ku_y9A&usqp=CAU",
    tech: "Arduino",
  },
  {
    image:
      "https://static-00.iconduck.com/assets.00/raspberry-pi-icon-2048x2048-p0y4r07x.png",
    tech: "Raspberry PI",
  },
  {
    image:
      "https://cdn.iconscout.com/icon/free/png-256/free-mysql-3628940-3030165.png",
    tech: "MySQL",
  },
];

const toolsList = [
  {
    image: "https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png",
    tech: "Git",
  },
  {
    image: "https://code.visualstudio.com/assets/branding/app-icon.png",
    tech: "VS Code",
  },
  {
    image: "https://www.svgrepo.com/show/354202/postman-icon.svg",
    tech: "Postman",
  },
];
//import mE from '/me.jpg';
export default defineComponent({
  name: "IndexPage",
  components: {
    ProfileComponent,
    MoreDetails,
    TechStacksCard,
    TechStackCardLabel,
  },
  data() {
    return {
      techStackList: techStackList,
      backendTechStackList: backendTechStackList,
      ioTTechStackList: ioTTechStackList,
      toolsList: toolsList,
    };
  },
});
</script>

```TS
import {
  Human,
  Coffee,
  Cappuccino,
  Language,
  TypescriptLanguage,
  React,
  Vue,
  NestJS,
  Jest,
} from '@mmintel/awesome';

interface Developer extends Human {
  code: () => void;
}

class Marc implements Developer {
  private frameworks: Framework[];
  
  constructor(
    private language: Language,
    private coffee: Coffee,
  ) {}
  
  public sayHello(): void {
    console.log(`
      Hi there 👋,
      
      I'm Marc, a Software Developer from Cologne, Germany.
      I love Typescript on client side, with NodeJS or Deno.
      I have a lot of experience with frontend frameworks like React or Vue.
      On the server side I prefer to work with Nestjs.
      I also like C# with Unity a lot but that's just for fun.
      
      I'm always interested to work on awesome projects, in that case you should contact me.
      
      Cheers
    `);
  }
  
  public addFramework(framework: Framework): void {
    this.frameworks.push(framework);
  }
  
  public async code(): void {
    await this.coffee.drink();
    
    for (const framework of this.frameworks) {
      await this.language.use(framework);
    }
    
    this.language.writeSomeCode();
  }
  
  public async test(): void {
    const jest = this.frameworks.find(f => f instanceOf Jest);
    jest.run();
  }
}

const language: Typescript = new TypescriptLanguage();
const coffe: Coffee = new Cappuccino();

const marc = new Marc(language, coffee);

marc.addFramework(React);
marc.addFramework(Vue);
marc.addFramework(NestJS);
marc.addFramework(Jest);

(async () => {
    marc.sayHello();
    try {
      await marc.code();
    } catch {
      await marc.test();
    }
})();
```

<!--
**mmintel/mmintel** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

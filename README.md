```TS
import {
  Human,
  Coffee,
  Cappuccino,
  Language,
  Typescript,
  React,
  Vue,
  NestJS,
  Jest,
} from '@mmintel/awesome';

interface Developer extends Human {
  test: () => void;
  code: () => void;
  addFramework: () => void;
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

const language: Language = new Typescript();
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

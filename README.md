{
  "name": "Hǎiyán Traduction",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  },
  "dependencies": {
    "next": "13.5.0",
    "react": "18.2.0",
    "react-dom": "18.2.0",
    "framer-motion": "^10.16.4",
    "@/components/ui": "latest" 
  },
  "devDependencies": {
    "typescript": "^5.3.0"
  }/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  images: {
    domains: [], // ajoute ici des domaines externes si tu utilises des images hébergées ailleurs
  },
};

module.exports = nextConfig;{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noEmit": true,
    "esModuleInterop": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "jsx": "preserve",
    "incremental": true
  },
  "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx"],
  "exclude": ["node_modules"]
}# dependencies
/node_modules

# build
/.next
/out

# misc
.DS_Store
.env.localgit init
git add .
git commit -m "Initial commit for Haiyan Traduction"git branch -M main
git remote add origin https://github.com/TON-UTILISATEUR/haiyan-traduction.git
git push -u origin mainimport { useEffect, useState } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input"; import Image from "next/image"; import { motion, AnimatePresence } from "framer-motion"; import logo from "@/public/logo.png"; import mireillePhoto from "@/public/mireille.jpg"; // Photo de Mireille officialisée import hero1 from "@/public/hero-library.jpg"; // Jeune homme en bibliothèque (ACCUEIL uniquement) import hero2 from "@/public/hero-tablet.jpg";  // Femme en robe bleue avec tablette (ACCUEIL uniquement)

export default function HaiyanTraduction() { const [lang, setLang] = useState("fr"); const [slide, setSlide] = useState(0); const heroSlides = [ { src: hero1, alt: "Illustration bibliothèque", caption: "Votre message, parfaitement traduit" }, { src: hero2, alt: "Illustration professionnelle", caption: "Communication sans limites" } ];

useEffect(() => { const id = setInterval(() => setSlide((s) => (s + 1) % heroSlides.length), 4500); return () => clearInterval(id); }, []);

const translations = { fr: { home: "Accueil", services: "Services", about: "À propos", missions: "Missions", team: "Notre Équipe", testimonials: "Témoignages", pricing: "Tarifs", contact: "Contact", title: "Hǎiyán Traduction", slogan: "Des mots qui unissent le monde.", ctaServices: "Nos services", ctaContact: "Contactez-nous", introTitle: "Votre partenaire pour une communication sans limites", introText: "Spécialisée en traduction chinois–français, anglais–français et en interprétation, Hǎiyán Traduction vous accompagne pour des textes fidèles, fluides et adaptés.", serviceList: [ "Traduction Chinois ↔ Français", "Traduction Français ↔ Anglais", "Interprétation et accompagnement linguistique", "Domaines de traduction : Général" ], aboutText: "Hǎiyán Traduction : Votre partenaire pour une communication sans limites. Fondée par Mireille, passionnée par les langues, notre mission est de fournir une excellence linguistique au service de vos ambitions internationales.", teamTitle: "Notre Équipe", teamBio: { name: "Mireille – Fondatrice & Traductrice principale", experience: [ "Traduction français ⇄ chinois pour le navire hôpital Arche de Paix.", "Traduction français ⇄ chinois au centre commercial chinois." ], formation: "Licence en Didactique du chinois à l’Institut Confucius.", enseignement: "Enseignante de langue chinoise au primaire.", passion: "Dévouée et passionnée par la langue chinoise, Mireille allie rigueur linguistique et sens pédagogique pour offrir des traductions authentiques et précises." }, missionTitle: "Nos missions", testimonials: [ { name: "Jean-Pierre, Entrepreneur", text: "Service rapide et précis, j’ai pu finaliser mon contrat avec des partenaires chinois sans aucune barrière linguistique." }, { name: "Sophie, Étudiante", text: "Grâce à Hǎiyán Traduction, mes documents académiques ont été traduits avec professionnalisme et clarté." } ], pricingText: "Nos tarifs standards :\n- Traduction Chinois ↔ Français : 0,20€/mot\n- Traduction Anglais ↔ Français : 0,10€/mot", contactText: "Envoyez-nous un message pour discuter de vos besoins en traduction.", send: "Envoyer", twitter: "Compte Twitter", whatsapp: "WhatsApp", email: "Email", quote: "Demander un devis via WhatsApp" }, en: { home: "Home", services: "Services", about: "About", missions: "Missions", team: "Our Team", testimonials: "Testimonials", pricing: "Pricing", contact: "Contact", title: "Hǎiyán Translation", slogan: "Words that unite the world.", ctaServices: "Our services", ctaContact: "Contact us", introTitle: "Your partner for borderless communication", introText: "Specialized in Chinese–French, English–French translation and interpretation, Hǎiyán Translation delivers faithful, fluent and adapted texts.", serviceList: [ "Chinese ↔ French Translation", "French ↔ English Translation", "Interpretation and linguistic support", "Translation domain: General" ], aboutText: "Hǎiyán Translation: Your partner for limitless communication. Founded by Mireille, passionate about languages, our mission is to provide linguistic excellence in the service of your international ambitions.", teamTitle: "Our Team", teamBio: { name: "Mireille – Founder & Lead Translator", experience: [ "French ⇄ Chinese translation for the hospital ship Peace Ark.", "French ⇄ Chinese translation at the Chinese Commercial Center." ], formation: "Bachelor's degree in Chinese Didactics from the Confucius Institute.", enseignement: "Chinese language teacher at primary school.", passion: "Dedicated and passionate about the Chinese language, Mireille combines linguistic rigor with pedagogical sense to deliver authentic and precise translations." }, missionTitle: "Our Missions", testimonials: [ { name: "John, Business Owner", text: "Professional and accurate translations that helped me close deals with Chinese partners smoothly." }, { name: "Emily, Student", text: "Clear and faithful translations of my academic documents. I highly recommend Hǎiyán Translation!" } ], pricingText: "Our standard rates:\n- Chinese ↔ French Translation: €0.20/word\n- English ↔ French Translation: €0.10/word", contactText: "Send us a message to discuss your translation needs.", send: "Send", twitter: "Twitter Account", whatsapp: "WhatsApp", email: "Email", quote: "Request a Quote via WhatsApp" }, zh: { home: "首页", services: "服务", about: "关于我们", missions: "使命", team: "我们的团队", testimonials: "客户评价", pricing: "价格", contact: "联系", title: "海燕翻译", slogan: "连接世界的文字。", ctaServices: "我们的服务", ctaContact: "联系我们", introTitle: "无国界沟通的合作伙伴", introText: "海燕翻译专注于中法、英法翻译及口译，提供忠实、流畅并契合场景的文本。", serviceList: ["中法翻译", "法英翻译", "口译及语言陪同", "翻译领域：综合"], aboutText: "海燕翻译：您无国界沟通的合作伙伴。由热爱语言的Mireille创立，我们的使命是提供卓越的语言服务，助力您的国际雄心。", teamTitle: "我们的团队", teamBio: { name: "Mireille – 创始人兼首席译员", experience: [ "为中国海军“和平方舟”医院船提供法汉互译。", "在中国商城进行法汉互译。" ], formation: "孔子学院中文教学法学士学位。", enseignement: "小学中文教师。", passion: "Mireille 热爱中文，既严谨又富有教学热情，致力于提供地道而精准的翻译服务。" }, missionTitle: "我们的使命", testimonials: [ { name: "王先生，公司负责人", text: "专业且准确的翻译，让我与法国合作伙伴的合同顺利完成。" }, { name: "李同学，学生", text: "学术文件翻译清晰到位，非常值得推荐！" } ], pricingText: "标准价格：\n- 中法翻译：每词0,20€\n- 法英翻译：每词0,10€", contactText: "欢迎联系我们，讨论您的翻译需求。", send: "发送", twitter: "推特账号", whatsapp: "WhatsApp", email: "电子邮件", quote: "通过 WhatsApp 请求报价" } } as const;

const t = translations[lang];

return ( <div className="min-h-screen bg-gray-50"> {/* HEADER */} <header className="flex justify-between items-center p-4 shadow-md bg-white sticky top-0 z-50"> <div className="flex items-center space-x-3"> <Image src={logo} alt="Hǎiyán Traduction Logo" width={50} height={50} /> <h1 className="text-2xl font-bold text-blue-700">{t.title}</h1> </div> <nav className="hidden md:flex gap-5 text-sm"> <a href="#home">{t.home}</a> <a href="#services">{t.services}</a> <a href="#about">{t.about}</a> <a href="#missions">{t.missions}</a> <a href="#team">{t.team}</a> <a href="#testimonials">{t.testimonials}</a> <a href="#pricing">{t.pricing}</a> <a href="#contact">{t.contact}</a> </nav> <div className="flex gap-2"> <Button variant="outline" size="sm" onClick={() => setLang("fr")}>FR</Button> <Button variant="outline" size="sm" onClick={() => setLang("en")}>EN</Button> <Button variant="outline" size="sm" onClick={() => setLang("zh")}>中文</Button> </div> </header>

{/* HERO / ACCUEIL */}
  <section id="home" className="relative h-[60vh] md:h-[72vh] overflow-hidden">
    <AnimatePresence>
      <motion.div key={slide} initial={{ opacity: 0, scale: 1.02 }} animate={{ opacity: 1, scale: 1 }} exit={{ opacity: 0 }} transition={{ duration: 0.8 }} className="absolute inset-0">
        <Image src={heroSlides[slide].src} alt={heroSlides[slide].alt} fill className="object-cover" priority />
        <div className="absolute inset-0 bg-black/40" />
      </motion.div>
    </AnimatePresence>
    <div className="relative z-10 h-full flex flex-col items-center justify-center text-center text-white px-4">
      <Image src={logo} alt="Logo" width={72} height={72} className="opacity-90" />
      <h2 className="mt-4 text-3xl md:text-5xl font-extrabold drop-shadow-lg text-balance">{t.slogan}</h2>
      <p className="mt-3 md:mt-4 max-w-3xl text-sm md:text-lg opacity-90">{t.introTitle}</p>
      <div className="mt-6 flex gap-3">
        <Button asChild className="bg-blue-600">
          <a href="#services">{t.ctaServices}</a>
        </Button>
        <Button asChild variant="outline" className="backdrop-blur bg-white/20 text-white border-white/40">
          <a href="#contact">{t.ctaContact}</a>
        </Button>
      </div>
      <div className="absolute bottom-4 left-1/2 -translate-x-1/2 flex gap-2">
        {heroSlides.map((_, i) => (
          <button key={i} onClick={() => setSlide(i)} className={`h-2 w-2 rounded-full ${i === slide ? "bg-white" : "bg-white/40"}`} aria-label={`slide-${i}`} />
        ))}
      </div>
    </div>
  </section>

  {/* INTRO avec illustration hero2 en vignette */}
  <section className="p-6 md:p-10 bg-white">
    <div className="mx-auto max-w-6xl grid md:grid-cols-2 gap-8 items-center">
      <div>
        <h3 className="text-2xl md:text-3xl font-semibold mb-3">{t.introTitle}</h3>
        <p className="text-gray-700 leading-relaxed">{t.introText}</p>
        <div className="mt-5 flex gap-3">
          <Button asChild className="bg-blue-600"><a href="#pricing">{t.pricing}</a></Button>
          <Button asChild variant="outline"><a href="#contact">{t.contact}</a></Button>
        </div>
      </div>
      <div className="relative aspect-[4/3] w-full overflow-hidden rounded-2xl shadow-lg">
        <Image src={hero2} alt="Illustration accueil" fill className="object-cover" />
      </div>
    </div>
  </section>

  {/* SERVICES */}
  <section id="services" className="p-8 md:p-12 grid md:grid-cols-3 gap-6 bg-gray-50">
    {t.serviceList.map((service, i) => (
      <Card key={i} className="shadow-lg rounded-2xl">
        <CardContent className="p-6 text-center font-medium">{service}</CardContent>
      </Card>
    ))}
  </section>

  {/* A PROPOS */}
  <section id="about" className="p-8 md:p-12 bg-white">
    <h3 className="text-2xl font-semibold mb-4">{t.about}</h3>
    <p className="text-gray-700">{t.aboutText}</p>
  </section>

  {/* MISSIONS */}
  <section id="missions" className="p-8 md:p-12 bg-gray-100">
    <h3 className="text-2xl font-semibold mb-6">{t.missionTitle}</h3>
    <ul className="space-y-4 list-disc list-inside text-gray-700 max-w-6xl">
      {translations[lang].missionList?.map((mission: string, i: number) => (
        <li key={i}>{mission}</li>
      ))}
    </ul>
  </section>

  {/* EQUIPE */}
  <section id="team" className="p-8 md:p-12 bg-white">
    <h3 className="text-2xl font-semibold mb-6">{t.teamTitle}</h3>
    <div className="flex flex-col md:flex-row items-center md:items-start gap-6">
      <Image src={mireillePhoto} alt="Portrait de Mireille" width={192} height={192} className="rounded-full w-48 h-48 object-cover ring-2 ring-blue-200 ring-offset-2 shadow-md" />
      <div>
        <h4 className="text-xl font-bold mb-2">{t.teamBio.name}</h4>
        <ul className="list-disc list-inside space-y-1 text-gray-700">
          {t.teamBio.experience.map((exp, i) => (
            <li key={i}>{exp}</li>
          ))}
        </ul>
        <p className="mt-3 text-gray-700"><strong>Formation :</strong> {t.teamBio.formation}</p>
        <p className="text-gray-700"><strong>Enseignement :</strong> {t.teamBio.enseignement}</p>
        <p className="mt-2 italic text-gray-600">{t.teamBio.passion}</p>
      </div>
    </div>
  </section>

  {/* TEMOIGNAGES */}
  <section id="testimonials" className="p-8 md:p-12 bg-gray-100">
    <h3 className="text-2xl font-semibold mb-6">{t.testimonials}</h3>
    <div className="grid md:grid-cols-2 gap-6 max-w-5xl mx-auto">
      {t.testimonials instanceof Array && t.testimonials.map((testi, i) => (


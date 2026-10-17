 
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Мир современных технологий</title>

  <style>
    :root {
      --bg: #f3f5f9;
      --card: #ffffff;
      --text: #202638;
      --muted: #596579;
      --accent: #3457d5;
      --header: #182447;
      --border: #dce2ed;
    }

    body.dark {
      --bg: #101522;
      --card: #1b2435;
      --text: #f3f5fb;
      --muted: #c0c9d8;
      --accent: #91a8ff;
      --header: #080d19;
      --border: #364156;
    }

    * {
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.7;
      transition: background 0.3s, color 0.3s;
    }

    header {
      background: linear-gradient(135deg, var(--header), #3457a5);
      color: white;
      padding: 45px 20px;
      text-align: center;
    }

    header h1 {
      margin: 0 0 10px;
      font-size: clamp(28px, 5vw, 44px);
    }

    header p {
      margin: 0;
      font-size: 18px;
    }

    nav {
      background: var(--card);
      border-bottom: 1px solid var(--border);
      padding: 12px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      gap: 12px;
      position: sticky;
      top: 0;
      z-index: 10;
    }

    nav a {
      color: var(--text);
      text-decoration: none;
      font-weight: bold;
      padding: 6px 10px;
      border-radius: 6px;
    }

    nav a:hover {
      background: var(--accent);
      color: white;
    }

    button {
      background: var(--accent);
      color: white;
      border: none;
      padding: 10px 16px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 15px;
    }

    button:hover {
      opacity: 0.85;
    }

    .language-buttons {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 15px;
    }

    .language-buttons button.active {
      outline: 2px solid var(--accent);
      outline-offset: 3px;
    }

    main {
      max-width: 1000px;
      margin: 25px auto;
      padding: 0 18px;
    }

    section.content-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 24px;
      margin-bottom: 22px;
      box-shadow: 0 4px 14px rgba(0, 0, 0, 0.04);
    }

    h2 {
      color: var(--accent);
      margin-top: 0;
    }

    .star-section {
      text-align: center;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 24px;
      margin-bottom: 22px;
    }

    .star {
      display: block;
      width: 220px;
      height: 220px;
      max-width: 80%;
      margin: 15px auto;
    }

    .star-caption {
      color: var(--muted);
      margin-bottom: 0;
    }

    .technology-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 16px;
    }

    .technology-item {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 18px;
    }

    .technology-item h3 {
      margin-top: 0;
    }

    .muted {
      color: var(--muted);
    }

    .quiz-option {
      display: block;
      margin: 10px 0;
      padding: 10px;
      border: 1px solid var(--border);
      border-radius: 8px;
      cursor: pointer;
    }

    .quiz-option:hover {
      background: var(--bg);
    }

    #quiz-result {
      font-weight: bold;
      margin-top: 15px;
    }

    footer {
      text-align: center;
      padding: 25px 15px;
      background: var(--header);
      color: white;
      margin-top: 35px;
    }

    @media (max-width: 600px) {
      header {
        padding: 32px 15px;
      }

      section.content-card,
      .star-section {
        padding: 18px;
      }

      nav {
        position: static;
      }
    }
  </style>
</head>

<body>

  <header>
    <h1 data-i18n="title">Мир современных технологий</h1>
    <p data-i18n="subtitle">Как технологии меняют нашу жизнь</p>

    <div class="language-buttons">
      <button type="button" data-lang="hy">🇦🇲 Հայերեն</button>
      <button type="button" data-lang="ru" class="active">🇷🇺 Русский</button>
      <button type="button" data-lang="en">🇺🇸 English</button>
    </div>
  </header>

  <nav>
    <a href="#home" data-i18n="navHome">Главная</a>
    <a href="#computer" data-i18n="navComputer">Компьютеры</a>
    <a href="#internet" data-i18n="navInternet">Интернет</a>
    <a href="#ai" data-i18n="navAI">Искусственный интеллект</a>
    <a href="#quiz" data-i18n="navQuiz">Викторина</a>
    <button id="theme-button" type="button">🌙 Тёмная тема</button>
  </nav>

  <main>

    <section class="star-section">
      <h2 data-i18n="starTitle">Чёрно-белая восьмиконечная звезда</h2>
      <p data-i18n="starDescription">
        Геометрическая звезда с восемью острыми лучами.
      </p>

      <svg class="star"
           viewBox="0 0 100 100"
           xmlns="http://www.w3.org/2000/svg"
           role="img"
           aria-label="Восьмиконечная звезда">

        <polygon points="50,2 61,39 98,50 61,61
                         50,98 39,61 2,50 39,39"
                 fill="#050505"/>

        <polygon points="50,2 50,50 39,39" fill="#ffffff"/>
        <polygon points="50,2 61,39 50,50" fill="#ffffff"/>

        <polygon points="98,50 50,50 61,39" fill="#ffffff"/>
        <polygon points="98,50 61,61 50,50" fill="#ffffff"/>

        <polygon points="50,98 50,50 61,61" fill="#ffffff"/>
        <polygon points="50,98 39,61 50,50" fill="#ffffff"/>

        <polygon points="2,50 50,50 39,61" fill="#ffffff"/>
        <polygon points="2,50 39,39 50,50" fill="#ffffff"/>

        <polygon points="50,2 61,39 98,50 61,61
                         50,98 39,61 2,50 39,39"
                 fill="none"
                 stroke="#777777"
                 stroke-width="0.6"/>
      </svg>

      <p class="star-caption" data-i18n="starCaption">
        Восьмиконечная звезда — геометрический узор из восьми лучей.
      </p>
    </section>

    <section class="content-card" id="home">
      <h2 data-i18n="welcome">Добро пожаловать!</h2>
      <p data-i18n="homeText1">
        Современные технологии стали важной частью нашей повседневной жизни.
        Мы используем телефоны, компьютеры и интернет для учёбы, работы,
        общения и развлечений.
      </p>
      <p data-i18n="homeText2">
        На этом сайте ты узнаешь о компьютерах, интернете и искусственном
        интеллекте, а в конце сможешь проверить свои знания.
      </p>
    </section>

    <section class="content-card" id="computer">
      <h2 data-i18n="computerTitle">💻 Компьютеры</h2>
      <p data-i18n="computerText">
        Компьютер — это электронное устройство, которое обрабатывает,
        хранит и передаёт информацию. Он помогает людям решать задачи,
        создавать проекты и изучать новые вещи.
      </p>

      <div class="technology-grid">
        <div class="technology-item">
          <h3 data-i18n="desktopTitle">Настольный компьютер</h3>
          <p data-i18n="desktopText">
            Подходит для учёбы, работы, программирования и игр.
          </p>
        </div>

        <div class="technology-item">
          <h3 data-i18n="laptopTitle">Ноутбук</h3>
          <p data-i18n="laptopText">
            Портативный компьютер, который удобно брать с собой.
          </p>
        </div>

        <div class="technology-item">
          <h3 data-i18n="tabletTitle">Планшет</h3>
          <p data-i18n="tabletText">
            Устройство с сенсорным экраном для чтения, учёбы и творчества.
          </p>
        </div>
      </div>
    </section>

    <section class="content-card" id="internet">
      <h2 data-i18n="internetTitle">🌐 Интернет</h2>
      <p data-i18n="internetText">
        Интернет соединяет миллионы устройств по всему миру. Благодаря ему
        люди могут общаться, находить информацию, смотреть видео и учиться
        на расстоянии.
      </p>

      <h3 data-i18n="safetyTitle">Как безопасно пользоваться интернетом?</h3>
      <ul>
        <li data-i18n="safety1">Не сообщай незнакомым людям свои пароли.</li>
        <li data-i18n="safety2">Не публикуй домашний адрес и личные данные.</li>
        <li data-i18n="safety3">Проверяй информацию в надёжных источниках.</li>
        <li data-i18n="safety4">Не открывай подозрительные ссылки и файлы.</li>
        <li data-i18n="safety5">Обращайся к взрослому, если что-то в интернете тебя тревожит.</li>
      </ul>
    </section>

    <section class="content-card" id="ai">
      <h2 data-i18n="aiTitle">🤖 Искусственный интеллект</h2>
      <p data-i18n="aiText">
        Искусственный интеллект (ИИ) — это технологии, которые позволяют
        компьютерам выполнять задачи, например распознавать изображения,
        понимать текст, переводить языки и помогать анализировать данные.
      </p>

      <div class="technology-grid">
        <div class="technology-item">
          <h3 data-i18n="educationTitle">Образование</h3>
          <p data-i18n="educationText">
            ИИ может объяснять темы, помогать с практикой и изучением языков.
          </p>
        </div>

        <div class="technology-item">
          <h3 data-i18n="medicineTitle">Медицина</h3>
          <p data-i18n="medicineText">
            ИИ помогает специалистам анализировать медицинские изображения и данные.
          </p>
        </div>

        <div class="technology-item">
          <h3 data-i18n="creativityTitle">Творчество</h3>
          <p data-i18n="creativityText">
            ИИ может помогать создавать изображения, музыку и идеи для проектов.
          </p>
        </div>
      </div>

      <p data-i18n="aiWarning">
        Важно помнить: искусственный интеллект может ошибаться.
        Поэтому важную информацию нужно проверять.
      </p>
    </section>

    <section class="content-card" id="quiz">
      <h2 data-i18n="quizTitle">🧠 Проверь свои знания</h2>
      <p id="question" data-i18n="question">
        1. Что помогает нам находить информацию в интернете?
      </p>

      <label class="quiz-option">
        <input type="radio" name="answer" value="a">
        <span data-i18n="optionA">Холодильник</span>
      </label>

      <label class="quiz-option">
        <input type="radio" name="answer" value="b">
        <span data-i18n="optionB">Веб-браузер</span>
      </label>

      <label class="quiz-option">
        <input type="radio" name="answer" value="c">
        <span data-i18n="optionC">Микроволновая печь</span>
      </label>

      <button id="check-button" type="button" data-i18n="checkAnswer">
        Проверить ответ
      </button>

      <p id="quiz-result" aria-live="polite"></p>
    </section>

  </main>

  <footer>
    <p data-i18n="footerCopyright">© 2026 Мир современных технологий</p>
    <p data-i18n="footerText">Учись, исследуй и открывай новое!</p>
  </footer>

  <script>
    const translations = {
      ru: {
        title: "Мир современных технологий",
        subtitle: "Как технологии меняют нашу жизнь",
        navHome: "Главная",
        navComputer: "Компьютеры",
        navInternet: "Интернет",
        navAI: "Искусственный интеллект",
        navQuiz: "Викторина",
        darkTheme: "🌙 Тёмная тема",
        lightTheme: "☀️ Светлая тема",
        starTitle: "Чёрно-белая восьмиконечная звезда",
        starDescription: "Геометрическая звезда с восемью острыми лучами.",
        starCaption: "Восьмиконечная звезда — геометрический узор из восьми лучей.",
        welcome: "Добро пожаловать!",
        homeText1: "Современные технологии стали важной частью нашей повседневной жизни. Мы используем телефоны, компьютеры и интернет для учёбы, работы, общения и развлечений.",
        homeText2: "На этом сайте ты узнаешь о компьютерах, интернете и искусственном интеллекте, а в конце сможешь проверить свои знания.",
        computerTitle: "💻 Компьютеры",
        computerText: "Компьютер — это электронное устройство, которое обрабатывает, хранит и передаёт информацию. Он помогает людям решать задачи, создавать проекты и изучать новые вещи.",
        desktopTitle: "Настольный компьютер",
        desktopText: "Подходит для учёбы, работы, программирования и игр.",
        laptopTitle: "Ноутбук",
        laptopText: "Портативный компьютер, который удобно брать с собой.",
        tabletTitle: "Планшет",
        tabletText: "Устройство с сенсорным экраном для чтения, учёбы и творчества.",
        internetTitle: "🌐 Интернет",
        internetText: "Интернет соединяет миллионы устройств по всему миру. Благодаря ему люди могут общаться, находить информацию, смотреть видео и учиться на расстоянии.",
        safetyTitle: "Как безопасно пользоваться интернетом?",
        safety1: "Не сообщай незнакомым людям свои пароли.",
        safety2: "Не публикуй домашний адрес и личные данные.",
        safety3: "Проверяй информацию в надёжных источниках.",
        safety4: "Не открывай подозрительные ссылки и файлы.",
        safety5: "Обращайся к взрослому, если что-то в интернете тебя тревожит.",
        aiTitle: "🤖 Искусственный интеллект",
        aiText: "Искусственный интеллект (ИИ) — это технологии, которые позволяют компьютерам выполнять задачи, например распознавать изображения, понимать текст, переводить языки и помогать анализировать данные.",
        educationTitle: "Образование",
        educationText: "ИИ может объяснять темы, помогать с практикой и изучением языков.",
        medicineTitle: "Медицина",
        medicineText: "ИИ помогает специалистам анализировать медицинские изображения и данные.",
        creativityTitle: "Творчество",
        creativityText: "ИИ может помогать создавать изображения, музыку и идеи для проектов.",
        aiWarning: "Важно помнить: искусственный интеллект может ошибаться. Поэтому важную информацию нужно проверять.",
        quizTitle: "🧠 Проверь свои знания",
        question: "1. Что помогает нам находить информацию в интернете?",
        optionA: "Холодильник",
        optionB: "Веб-браузер",
        optionC: "Микроволновая печь",
        checkAnswer: "Проверить ответ",
        noAnswer: "Пожалуйста, выбери ответ.",
        correct: "✅ Правильно! Веб-браузер помогает открывать сайты.",
        incorrect: "❌ Не совсем! Попробуй ещё раз.",
        footerCopyright: "© 2026 Мир современных технологий",
        footerText: "Учись, исследуй и открывай новое!"
      },

      hy: {
        title: "Ժամանակակից տեխնոլոգիաների աշխարհը",
        subtitle: "Ինչպես են տեխնոլոգիաները փոխում մեր կյանքը",
        navHome: "Գլխավոր",
        navComputer: "Համակարգիչներ",
        navInternet: "Ինտերնետ",
        navAI: "Արհեստական բանականություն",
        navQuiz: "Վիկտորինա",
        darkTheme: "🌙 Մուգ թեմա",
        lightTheme: "☀️ Բաց թեմա",
        starTitle: "Սև-սպիտակ ութաթև աստղ",
        starDescription: "Երկրաչափական աստղ՝ ութ սուր ճառագայթներով։",
        starCaption: "Ութաթև աստղը ութ ճառագայթներից կազմված երկրաչափական պատկեր է։",
        welcome: "Բարի գալուստ։",
        homeText1: "Ժամանակակից տեխնոլոգիաները դարձել են մեր առօրյա կյանքի կարևոր մասը։ Մենք օգտագործում ենք հեռախոսներ, համակարգիչներ և ինտերնետ՝ սովորելու, աշխատելու, շփվելու և զվարճանալու համար։",
        homeText2: "Այս կայքում դու կիմանաս համակարգիչների, ինտերնետի և արհեստական բանականության մասին, իսկ վերջում կկարողանաս ստուգել գիտելիքներդ։",
        computerTitle: "💻 Համակարգիչներ",
        computerText: "Համակարգիչը էլեկտրոնային սարք է, որը մշակում, պահպանում և փոխանցում է տեղեկությունը։ Այն օգնում է մարդկանց լուծել խնդիրներ, ստեղծել նախագծեր և նոր բաներ սովորել։",
        desktopTitle: "Սեղանի համակարգիչ",
        desktopText: "Հարմար է սովորելու, աշխատելու, ծրագրավորելու և խաղեր խաղալու համար։",
        laptopTitle: "Նոթբուք",
        laptopText: "Դյուրակիր համակարգիչ, որը հարմար է վերցնել քեզ հետ։",
        tabletTitle: "Պլանշետ",
        tabletText: "Սենսորային էկրանով սարք՝ կարդալու, սովորելու և ստեղծագործելու համար։",
        internetTitle: "🌐 Ինտերնետ",
        internetText: "Ինտերնետը կապում է միլիոնավոր սարքեր ամբողջ աշխարհում։ Դրա շնորհիվ մարդիկ կարող են շփվել, տեղեկություններ գտնել, տեսանյութեր դիտել և հեռավար սովորել։",
        safetyTitle: "Ինչպե՞ս անվտանգ օգտվել ինտերնետից։",
        safety1: "Անծանոթ մարդկանց մի՛ հայտնիր քո գաղտնաբառերը։",
        safety2: "Մի՛ հրապարակիր տան հասցեն և անձնական տվյալները։",
        safety3: "Տեղեկությունը ստուգիր վստահելի աղբյուրներում։",
        safety4: "Մի՛ բացիր կասկածելի հղումներ և ֆայլեր։",
        safety5: "Եթե ինտերնետում ինչ-որ բան քեզ անհանգստացնում է, դիմիր մեծահասակի։",
        aiTitle: "🤖 Արհեստական բանականություն",
        aiText: "Արհեստական բանականությունը տեխնոլոգիաների մի խումբ է, որը համակարգիչներին թույլ է տալիս կատարել տարբեր առաջադրանքներ՝ ճանաչել պատկերներ, հասկանալ տեքստը, թարգմանել լեզուներ և վերլուծել տվյալներ։",
        educationTitle: "Կրթություն",
        educationText: "Արհեստական բանականությունը կարող է բացատրել թեմաները և օգնել վարժություններ կատարել ու լեզուներ սովորել։",
        medicineTitle: "Բժշկություն",
        medicineText: "Արհեստական բանականությունն օգնում է մասնագետներին վերլուծել բժշկական պատկերներն ու տվյալները։",
        creativityTitle: "Ստեղծագործություն",
        creativityText: "Արհեստական բանականությունը կարող է օգնել ստեղծել պատկերներ, երաժշտություն և նախագծերի գաղափարներ։",
        aiWarning: "Կարևոր է հիշել, որ արհեստական բանականությունը կարող է սխալվել։ Այդ պատճառով կարևոր տեղեկությունը պետք է ստուգել։",
        quizTitle: "🧠 Ստուգիր գիտելիքներդ",
        question: "1. Ի՞նչն է օգնում մեզ ինտերնետում տեղեկություններ գտնել։",
        optionA: "Սառնարան",
        optionB: "Վեբ զննարկիչ",
        optionC: "Միկրոալիքային վառարան",
        checkAnswer: "Ստուգել պատասխանը",
        noAnswer: "Խնդրում եմ, ընտրիր պատասխանը։",
        correct: "✅ Ճիշտ է։ Վեբ զննարկիչը օգնում է բացել կայքերը։",
        incorrect: "❌ Ոչ այնքան։ Փորձիր կրկին։",
        footerCopyright: "© 2026 Ժամանակակից տեխնոլոգիաների աշխարհը",
        footerText: "Սովորիր, ուսումնասիրիր և բացահայտիր նորը։"
      },

      en: {
        title: "The World of Modern Technology",
        subtitle: "How technology is changing our lives",
        navHome: "Home",
        navComputer: "Computers",
        navInternet: "Internet",
        navAI: "Artificial Intelligence",
        navQuiz: "Quiz",
        darkTheme: "🌙 Dark Theme",
        lightTheme: "☀️ Light Theme",
        starTitle: "Black and White Eight-Pointed Star",
        starDescription: "A geometric star with eight sharp points.",
        starCaption: "An eight-pointed star is a geometric design with eight rays.",
        welcome: "Welcome!",
        homeText1: "Modern technology has become an important part of our daily lives. We use phones, computers, and the internet for studying, working, communicating, and entertainment.",
        homeText2: "On this website, you will learn about computers, the internet, and artificial intelligence. At the end, you can test your knowledge.",
        computerTitle: "💻 Computers",
        computerText: "A computer is an electronic device that processes, stores, and transfers information. It helps people solve problems, create projects, and learn new things.",
        desktopTitle: "Desktop Computer",
        desktopText: "Useful for studying, working, programming, and gaming.",
        laptopTitle: "Laptop",
        laptopText: "A portable computer that is easy to take with you.",
        tabletTitle: "Tablet",
        tabletText: "A touchscreen device for reading, learning, and creativity.",
        internetTitle: "🌐 Internet",
        internetText: "The internet connects millions of devices around the world. It allows people to communicate, find information, watch videos, and learn remotely.",
        safetyTitle: "How can you use the internet safely?",
        safety1: "Never share your passwords with strangers.",
        safety2: "Do not publish your home address or personal information.",
        safety3: "Check information using reliable sources.",
        safety4: "Do not open suspicious links or files.",
        safety5: "Talk to an adult if something online makes you uncomfortable.",
        aiTitle: "🤖 Artificial Intelligence",
        aiText: "Artificial intelligence (AI) is technology that allows computers to perform tasks such as recognizing images, understanding text, translating languages, and analyzing data.",
        educationTitle: "Education",
        educationText: "AI can explain topics and help with practice and language learning.",
        medicineTitle: "Medicine",
        medicineText: "AI helps professionals analyze medical images and data.",
        creativityTitle: "Creativity",
        creativityText: "AI can help create images, music, and ideas for projects.",
        aiWarning: "Remember that artificial intelligence can make mistakes. Important information should always be checked.",
        quizTitle: "🧠 Test Your Knowledge",
        question: "1. What helps us find information on the internet?",
        optionA: "A refrigerator",
        optionB: "A web browser",
        optionC: "A microwave oven",
        checkAnswer: "Check Answer",
        noAnswer: "Please choose an answer.",
        correct: "✅ Correct! A web browser helps you open websites.",
        incorrect: "❌ Not quite! Try again.",
        footerCopyright: "© 2026 The World of Modern Technology",
        footerText: "Learn, explore, and discover something new!"
      }
    };

    let currentLanguage = "ru";

    const themeButton = document.getElementById("theme-button");
    const checkButton = document.getElementById("check-button");
    const quizResult = document.getElementById("quiz-result");

    function updateThemeButton() {
      const isDark = document.body.classList.contains("dark");
      themeButton.textContent = isDark
        ? translations[currentLanguage].lightTheme
        : translations[currentLanguage].darkTheme;
    }

    function setLanguage(language) {
      if (!translations[language]) return;

      currentLanguage = language;
      document.documentElement.lang = language;

      document.querySelectorAll("[data-i18n]").forEach(function (element) {
        const key = element.dataset.i18n;
        element.textContent = translations[language][key];
      });

      document.querySelectorAll("[data-lang]").forEach(function (button) {
        button.classList.toggle(
          "active",
          button.dataset.lang === language
        );
      });

      quizResult.textContent = "";
      updateThemeButton();
    }

    document.querySelectorAll("[data-lang]").forEach(function (button) {
      button.addEventListener("click", function () {
        setLanguage(button.dataset.lang);
      });
    });

    themeButton.addEventListener("click", function () {
      document.body.classList.toggle("dark");
      updateThemeButton();
    });

    checkButton.addEventListener("click", function () {
      const selected = document.querySelector(
        'input[name="answer"]:checked'
      );

      if (!selected) {
        quizResult.textContent =
          translations[currentLanguage].noAnswer;
        return;
      }

      if (selected.value === "b") {
        quizResult.textContent =
          translations[currentLanguage].correct;
      } else {
        quizResult.textContent =
          translations[currentLanguage].incorrect;
      }
    });

    setLanguage("ru");
  </script>

</body>
</html>

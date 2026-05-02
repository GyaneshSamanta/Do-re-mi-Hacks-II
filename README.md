# Musicallywin.us

> **Train kids' analytical brains through music — two mini-games, one Express app, real SMS feedback.**

![Game preview](assets/img/1.jpg)

![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![Twilio](https://img.shields.io/badge/Twilio-F22F46?logo=twilio&logoColor=white)

[Watch the demo on YouTube](https://youtu.be/gHjMCvwVGhI)

## About

- **What:** A web app of music-based mini-games that test listening, memory, and logical deduction, with a Twilio SMS hook that sends parents progress updates.
- **Who:** Team Lead Gyanesh Samanta, full-stack dev Pratik Pattnaik, and Twilio dev Abhisekh.
- **When:** Built over the do-re-mi-hacks-II hackathon weekend, February 20, 2022.
- **Where:** Submitted to **do-re-mi-hacks II**, an MLH-affiliated music-themed hackathon.
- **Why:** Standard aptitude tests bore kids. Music doesn't. We bet that wrapping listening and memory tasks in a game-shaped interface would keep them engaged long enough to actually measure something useful.

## The Story

Every parent worth their salt has googled "aptitude test for kids" at least once. The results are uniformly grim — clip-art worksheets, multiple-choice grids, and the kind of UI design that screams *circa 2007*. We thought: what if the test was a game, and what if the medium was music?

Musicallywin.us is the result. Two mini-games sit inside an Express + EJS web app — one tests musical pattern recall, the other tests logical deduction from audio cues. After a session, Twilio fires off an SMS to the parent's phone with a snapshot of how the child performed, so progress is visible without anyone having to log back in.

We'd planned five games. We shipped two. The hackathon clock and the Twilio auth dance ate the rest, but the architecture is set up to drop more games in as plug-in routes — exactly what "What's next" exists for.

## Gallery

![Screen 1](assets/img/2.jpg)
![Screen 2](assets/img/3.jpg)
![Screen 3](assets/img/4.jpg)

---

## Tech Stack

- **Frontend:** HTML, CSS, vanilla JS, EJS templates (with `express-ejs-layouts`)
- **Backend:** Node.js 17, Express 4
- **Auth & sessions:** Passport (local), express-session, connect-mongo, cookie-parser
- **Storage:** MongoDB via Mongoose
- **Notifications:** Twilio SMS, Nodemailer
- **Other:** Multer (uploads), node-sass-middleware, googleapis, dotenv
- **Tooling:** Git, Canva (assets), DaVinci Resolve (demo video)

## Repo Structure

```
Do-re-mi-Hacks-II/
├── index.js              # Express entry point
├── package.json
├── config/               # DB + Passport config
├── controllers/          # Route handlers
├── routes/               # Express routes
├── models/               # Mongoose schemas
├── views/                # EJS templates
├── assets/               # Static images, CSS, client JS
└── Twilio/               # SMS integration
```

## Getting Started

```bash
git clone https://github.com/GyaneshSamanta/Do-re-mi-Hacks-II.git
cd Do-re-mi-Hacks-II
npm install
```

Create a `.env` with your `MONGODB_URI`, Twilio credentials (`TWILIO_SID`, `TWILIO_TOKEN`, `TWILIO_FROM`), and any session secret. Then:

```bash
npm start
```

The app boots on the port configured in `index.js`. Node 17.x is recommended (matches `engines` in `package.json`).

## Contributing

Pull requests welcome — the natural extension is adding more mini-games as new route + view modules and a unified score endpoint.

## License

[MIT](package.json).

## Credits

| Role | Contributor |
| :--- | :---------- |
| Team Lead | [Gyanesh Samanta](https://github.com/GyaneshSamanta) |
| Full-stack dev | [Pratik Pattnaik](https://github.com/pratik-chandrasekhar-pattanaik) |
| Twilio dev | [Abhisekh](https://github.com/abhishek213-alb) |

Built at do-re-mi-hacks II, organized by Major League Hacking (MLH).

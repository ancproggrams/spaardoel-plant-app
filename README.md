# 🌱 Spaardoel Plant App

Een interactieve web applicatie die kinderen helpt bij het sparen door hun voortgang te visualiseren als een groeiende plant. Naarmate ze dichter bij hun spaardoel komen, groeit hun virtuele plant van zaad tot bloeiende bloem.

## ✨ Features

### 🎯 Core Functionaliteiten
- **Profiel Management**: Ouder en kind profielen met verschillende toegangsniveaus
- **Spaardoel Beheer**: Maak en beheer meerdere spaardoelen met target bedragen en deadlines
- **Plant Visualisatie**: SVG-gebaseerde plant die groeit op basis van spaarvoortgang
- **Bijdrage Tracking**: Voeg geld toe en volg voortgang naar het doel
- **Deelbare Links**: Deel spaardoelen met familie en vrienden voor ondersteuning
- **Responsive Design**: Werkt op desktop, tablet en mobiele apparaten

### 🌿 Plant Groeistadia
- **Zaad** (0-10%): De start van het spaaravontuur
- **Kiemling** (10-25%): Eerste tekenen van groei
- **Kleine Plant** (25-50%): Stevige groei met bladeren
- **Middelgrote Plant** (50-75%): Meer bladeren en hoogte
- **Grote Plant** (75-95%): Bijna klaar om te bloeien
- **Bloeiende Plant** (95-100%): Prachtige bloem als beloning
- **Vruchtdragende Plant** (100%): Doel bereikt met vruchten van inspanning

### 👥 Gebruikersrollen
- **Ouders**: Volledige controle over doelen, kunnen geld toevoegen en voortgang monitoren
- **Kinderen**: Kunnen hun plant bekijken, voortgang volgen en gemotiveerd blijven

## 🚀 Installatie

### Vereisten
- Node.js 18.0 of hoger
- Yarn package manager
- PostgreSQL database (of SQLite voor development)

### Setup Instructies

1. **Clone de repository**
   ```bash
   git clone https://github.com/ancproggrams/spaardoel-plant-app.git
   cd spaardoel-plant-app
   ```

2. **Installeer dependencies**
   ```bash
   cd app
   yarn install
   ```

3. **Database setup**
   ```bash
   # Kopieer environment variabelen
   cp .env.example .env
   
   # Bewerk .env met je database credentials
   # DATABASE_URL="postgresql://username:password@localhost:5432/spaardoel_db"
   
   # Run database migraties
   npx prisma migrate dev
   
   # Seed de database (optioneel)
   yarn prisma db seed
   ```

4. **Start de development server**
   ```bash
   yarn dev
   ```

5. **Open de applicatie**
   Ga naar [http://localhost:3000](http://localhost:3000) in je browser

## 🛠️ Development

### Project Structuur
```
app/
├── app/                    # Next.js App Router
│   ├── dashboard/         # Dashboard paginas
│   ├── goals/            # Spaardoel management
│   ├── auth/             # Authenticatie
│   └── api/              # API routes
├── components/           # Herbruikbare React components
│   ├── ui/              # UI componenten (shadcn/ui)
│   └── plant-visualization.tsx  # Plant visualisatie component
├── lib/                 # Utility functies en configuratie
├── prisma/             # Database schema en migraties
├── hooks/              # Custom React hooks
└── scripts/            # Database seeding scripts
```

### Tech Stack
- **Frontend**: Next.js 14, React 18, TypeScript
- **Styling**: Tailwind CSS, Framer Motion voor animaties
- **Database**: Prisma ORM met PostgreSQL
- **Authentication**: NextAuth.js
- **UI Components**: Radix UI, shadcn/ui
- **Forms**: React Hook Form met Zod validatie
- **State Management**: Zustand, React Query

### Development Commands
```bash
# Start development server
yarn dev

# Build voor productie
yarn build

# Start productie server
yarn start

# Run linting
yarn lint

# Database commands
npx prisma studio          # Open database browser
npx prisma migrate dev     # Run nieuwe migraties
npx prisma generate        # Genereer Prisma client
npx prisma db seed         # Seed database
```

## 🎨 Customization

### Plant Types
De app ondersteunt verschillende plant types die kunnen worden geconfigureerd:
- Zonnebloem (standaard)
- Roos
- Tulp
- Madeliefje

### Kleuren en Styling
Pas de plant kleuren aan in `components/plant-visualization.tsx`:
```typescript
const getPlantColor = () => {
  switch (plantType) {
    case 'rose': return '#ff6b9d';
    case 'tulip': return '#c44569';
    case 'daisy': return '#f8b500';
    default: return '#ffd700'; // sunflower
  }
};
```

## 🔧 Configuration

### Environment Variables
```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/spaardoel_db"

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key"

# Optional: External integrations
SMTP_HOST="smtp.gmail.com"
SMTP_PORT="587"
SMTP_USER="your-email@gmail.com"
SMTP_PASS="your-app-password"
```

## 📱 Deployment

### Vercel (Aanbevolen)
1. Push code naar GitHub
2. Connect repository in Vercel dashboard
3. Configureer environment variables
4. Deploy automatisch bij elke push

### Docker
```bash
# Build image
docker build -t spaardoel-plant-app .

# Run container
docker run -p 3000:3000 spaardoel-plant-app
```

## 🤝 Contributing

1. Fork de repository
2. Maak een feature branch (`git checkout -b feature/nieuwe-functie`)
3. Commit je wijzigingen (`git commit -am 'Voeg nieuwe functie toe'`)
4. Push naar de branch (`git push origin feature/nieuwe-functie`)
5. Maak een Pull Request

## 📄 License

Dit project is gelicenseerd onder de MIT License - zie het [LICENSE](LICENSE) bestand voor details.

## 🙏 Acknowledgments

- Plant SVG animaties geïnspireerd door natuurlijke groeipatronen
- UI componenten gebaseerd op shadcn/ui design system
- Dank aan alle contributors die hebben geholpen bij de ontwikkeling

## 📞 Support

Voor vragen of ondersteuning, maak een issue aan in de GitHub repository of neem contact op via [email].

---

**Happy Saving! 🌱💰**
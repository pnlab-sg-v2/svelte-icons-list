# Svelte Icons List

A Svelte-based emoji browser with search functionality. Browse and search through a collection of emojis with a clean, responsive interface.

## Features

- **Emoji Grid Display**: View emojis in a 10-column grid layout
- **Virtual Scrolling**: Efficient rendering of large emoji lists using `@sveltejs/svelte-virtual-list`
- **Search Functionality**: Filter emojis by typing characters in the search box
- **Real-time Results**: See the count of matching emojis as you search
- **Responsive Design**: Clean and modern UI

## Development

### Prerequisites
- Node.js 18 or higher
- npm

### Setup
```bash
npm install
```

### Run Development Server
```bash
npm run dev
```

### Build for Production
```bash
npm run build
```

### Preview Production Build
```bash
npm run serve
```

## Deployment

This project includes a GitHub Actions workflow that automatically deploys to GitHub Pages when changes are pushed to the `main` branch.

### Setting up GitHub Pages

1. Go to your repository Settings
2. Navigate to Pages (under Code and automation)
3. Under "Build and deployment", set:
   - Source: **GitHub Actions**
4. Push your changes to the `main` branch
5. The site will be automatically deployed to `https://<username>.github.io/svelte-icons-list/`

The deployment workflow can also be triggered manually from the Actions tab.

## Tech Stack

- [Svelte](https://svelte.dev/) - Frontend framework
- [Vite](https://vitejs.dev/) - Build tool
- [@sveltejs/svelte-virtual-list](https://github.com/sveltejs/svelte-virtual-list) - Virtual scrolling
- GitHub Actions - CI/CD pipeline


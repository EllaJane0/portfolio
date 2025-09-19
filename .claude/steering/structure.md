# Project Structure & Architecture

## Repository Overview
This is a Quarto-based static website repository following a content-first architecture pattern. The structure prioritizes ease of content management, maintainability, and automated deployment workflows.

## Directory Structure
```
portfolio/
├── .github/
│   └── workflows/
│       └── publish.yml          # GitHub Actions deployment workflow
├── .claude/
│   ├── settings.local.json      # Claude Code local settings
│   └── steering/                # Project steering documents
├── .quarto/                     # Quarto build cache (auto-generated)
├── _site/                       # Built website output (auto-generated)
├── ccspecdev/                   # Spec development tools (separate project)
├── projects/                    # Project showcase pages
│   ├── project-1.qmd           # Flappy Goose case study
│   ├── project-2.qmd           # Additional project pages
│   └── project-[n].qmd         # Future project showcases
├── _quarto.yml                 # Site configuration and navigation
├── index.qmd                   # Homepage content
├── about.qmd                   # About page content
├── styles.css                  # Custom CSS overrides
├── vercel.json                 # Vercel deployment configuration
├── ella.jpg                    # Profile image
├── Ella_Moore_Resume.pdf       # Resume document
└── README.md                   # Project documentation
```

## Architecture Patterns

### Content Management Architecture
- **File-Based CMS**: Content stored as Quarto Markdown (.qmd) files
- **Frontmatter Configuration**: YAML metadata in each content file
- **Asset Co-location**: Related assets stored in logical proximity to content
- **Navigation Binding**: Central navigation defined in `_quarto.yml`

### Build & Deployment Architecture
- **Source Control**: Git-based version control with GitHub
- **Build Pipeline**: Quarto render → static file generation → deployment
- **Dual Deployment**: GitHub Pages (primary) + Vercel (alternative)
- **Automated Publishing**: Push-to-deploy via GitHub Actions

### Styling Architecture
- **Theme Foundation**: Bootstrap 5 "cosmo" theme as base
- **CSS Override Pattern**: Custom styles in single `styles.css` file
- **CSS Variables**: Centralized color scheme and design tokens
- **Component-Based Styling**: Reusable CSS classes for common patterns

## File Organization Principles

### Content Hierarchy
1. **Root Level**: Core pages (homepage, about) and global assets
2. **Projects Directory**: Detailed project case studies and showcases
3. **Configuration Files**: Site-wide settings and deployment configs
4. **Generated Content**: Build artifacts in `_site/` (ignored in version control)

### Naming Conventions
- **Page Files**: Descriptive names (`about.qmd`, `index.qmd`)
- **Project Files**: Numbered sequence (`project-1.qmd`, `project-2.qmd`)
- **Asset Files**: Descriptive, web-safe filenames (`ella.jpg`, `Ella_Moore_Resume.pdf`)
- **Config Files**: Standard naming for tools (`_quarto.yml`, `vercel.json`)

### Content Relationships
- **Navigation Structure**: Hierarchical menu structure in `_quarto.yml`
- **Cross-References**: Internal linking between related content
- **Asset References**: Relative path linking to images and documents
- **External Links**: Social media and professional profile integration

## Development Workflow Patterns

### Content Creation Workflow
1. **New Content**: Create `.qmd` file with proper frontmatter
2. **Navigation Update**: Add page to `_quarto.yml` navigation structure
3. **Asset Management**: Add related images/documents to appropriate location
4. **Preview**: Use `quarto preview` for local development
5. **Deploy**: Commit and push for automated deployment

### Project Showcase Workflow
1. **Project Documentation**: Create detailed `.qmd` file in `projects/` directory
2. **Asset Collection**: Gather project images, demos, documentation
3. **Case Study Development**: Write comprehensive project narrative
4. **Integration**: Link from homepage and navigation menu
5. **Maintenance**: Regular updates as projects evolve

### Style Development Workflow
1. **Design Changes**: Modify CSS variables and component styles
2. **Local Testing**: Preview changes with `quarto preview`
3. **Cross-Device Testing**: Verify responsive design behavior
4. **Performance Check**: Ensure CSS changes don't impact load times
5. **Deployment**: Push changes for automatic site rebuilding

## Scalability Considerations

### Content Scaling
- **Project Growth**: Numbered project files support unlimited project additions
- **Category Organization**: Future category-based organization possible
- **Search Integration**: Quarto supports search index generation
- **Multi-Language**: Framework supports internationalization if needed

### Technical Scaling
- **Performance**: Static site architecture ensures fast loading
- **Hosting Flexibility**: Multiple deployment targets (GitHub Pages, Vercel)
- **CDN Integration**: Hosting platforms provide global content distribution
- **Caching Strategy**: Browser and CDN caching for optimal performance

### Maintenance Scaling
- **Automation**: GitHub Actions handles build and deployment
- **Version Control**: Full history and rollback capabilities
- **Asset Management**: Centralized asset storage with relative linking
- **Configuration Management**: Single source of truth in `_quarto.yml`

## Integration Points

### External Service Integration
- **Social Media**: LinkedIn, GitHub profile linking
- **Professional Platforms**: Resume hosting and direct access
- **Project Hosting**: Live demo integration (Vercel apps)
- **Version Control**: GitHub repository showcasing

### Development Tool Integration
- **Claude Code**: AI-assisted development and content creation
- **GitHub Actions**: Automated testing and deployment
- **Quarto Ecosystem**: Compatible with R/Python data science workflows
- **Web Analytics**: Ready for Google Analytics or similar integration

## Security & Compliance

### Data Security
- **Public Repository**: All content considered public
- **No Sensitive Data**: No credentials, personal information beyond professional bio
- **Static Assets Only**: No server-side processing or data collection
- **HTTPS Enforcement**: Secure connections via hosting platform SSL

### Professional Compliance
- **Copyright Compliance**: All images and content properly licensed
- **Privacy Considerations**: Professional information only, no personal details
- **Professional Standards**: Content appropriate for employer/recruiter viewing
- **Link Integrity**: External links regularly verified for professional appropriateness
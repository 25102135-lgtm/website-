# website-

A lightweight front-end project intended to translate a Figma-driven UI/UX design into a clean, production-ready website experience.

## Design & UI/UX workflow

This repository is connected to the visual design workflow through Figma. All UI work should begin from approved design files and then be implemented here.

### Primary Figma file

- https://www.figma.com/make/go0fb6M6rjojjr5Liezb6V/CampusKart-Web-App-Design?code-node-id=0-6&p=f&t=WDGZH6vklKzWoT4V-0&fullscreen=1

### Design references

- Design system / component library
- Brand guidelines
- Landing-page wireframes and flows
- Interactive prototype

## Project purpose

- Build the website from Figma specifications
- Maintain consistent spacing, typography, and colors
- Align implementation with the design system
- Ensure accessibility in all UI updates

## Design-to-development process

1. Design is created or updated in Figma
2. Design is reviewed and approved
3. Implementation work is tracked in GitHub issues
4. UI changes are implemented in code
5. Pull requests reference the Figma design and include screenshots

## Repository conventions

- Place reusable UI elements in `src/components/`
- Keep styles centralized in `src/styles/` or equivalent
- Use accessible color contrast and semantic markup
- Add visual QA notes in the PR description when UI changes are included

## Related docs

- [Design Documentation](./DESIGN.md)
- [Issue Template](./.github/ISSUE_TEMPLATE/design-task.md)
- [Pull Request Template](./.github/pull_request_template.md)

## Quick start

```bash
npm install
npm run dev
```

> Update this section with the actual project scripts once the app structure is in place.

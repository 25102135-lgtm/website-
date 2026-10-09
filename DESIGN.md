# Figma Design Integration

This repository is intended to be aligned with a Figma-based UI/UX workflow. The goal is to keep product design, engineering, and review in sync from concept to implementation.

## Figma project

Use the official design file for all approved interface decisions:

- Figma: https://www.figma.com/make/go0fb6M6rjojjr5Liezb6V/CampusKart-Web-App-Design?code-node-id=0-6&p=f&t=WDGZH6vklKzWoT4V-0&fullscreen=1

## Design responsibilities

### Design team

- Create and maintain the user experience
- Define UI patterns and interaction flows
- Review design consistency and usability
- Publish approved states for engineering handoff

### Development team

- Implement the Figma designs in code
- Match spacing, typography, hierarchy, and components
- Confirm accessibility and responsiveness
- Keep implementation aligned with the approved design system

## Design system checklist

Before implementing a page or component, confirm:

- Figma mockup is approved
- Responsive behavior has been defined
- Interactive states are documented
- Color tokens and spacing values are known
- Images or icons are available in the correct format

## Handoff workflow

1. Create or update the design in Figma
2. Add notes for required behavior and states
3. Share the link in the relevant GitHub issue or PR
4. Implement the UI in the codebase
5. Validate against the approved design and publish screenshots in the PR

## Asset and styling expectations

- Reuse shared UI primitives instead of creating inconsistent variations
- Keep styles centralized and maintainable
- Prefer system-aligned tokens over hardcoded values
- Document any exceptions clearly in the issue or PR

## Acceptance criteria for UI work

The work is complete when:

- The implementation matches the approved Figma screens
- All key states are covered
- The UI is responsive and accessible
- The final commit or PR includes the Figma reference

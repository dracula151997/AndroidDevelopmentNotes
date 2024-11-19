Here's a table view that outlines how each color in the `LightColorScheme` should be used for UI components:

| **Color**               | **Description**                                                                                          | **Components**                                                                                           |
|-------------------------|----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| **primary (Main500)**   | Main color for key actions, branding, and primary elements.                                              | App bar background, primary buttons, active tabs, toggles, sliders, and links.                           |
| **onPrimary (White)**   | Text/icons displayed on primary-colored elements.                                                        | Text/icons on primary buttons, app bar titles, and icons.                                               |
| **background**          | Main app background.                                                                                     | Screen backgrounds, base-level container backgrounds.                                                   |
| **onBackground (Black)**| Text or elements displayed on the background.                                                            | Main content text, headings, primary labels, and icons.                                                 |
| **surface (White)**     | Surfaces that are distinct from the main background.                                                     | Cards, modals, dialogs, menus, sheets.                                                                  |
| **onSurface (Black)**   | Text or elements displayed on surfaces.                                                                 | Text/icons in cards, modals, or sheets.                                                                 |
| **error (Red)**         | Error messages and components.                                                                           | Error messages, input field error states, banners with errors.                                          |
| **onError (White)**     | Text/icons displayed on error elements.                                                                  | Text/icons within error banners or error-colored buttons.                                               |
| **surfaceVariant**      | Variation of surface color for subtle differentiation.                                                   | Containers, secondary cards, dividers for sections.                                                     |
| **surfaceContainer**    | More pronounced variation for surface differentiation.                                                   | Secondary containers, UI separators.                                                                    |
| **secondary (Orange500)**| Color for secondary actions and accents.                                                                | Floating action buttons, secondary icons, highlighted borders, secondary buttons.                       |
| **onSecondary (White)** | Text/icons displayed on secondary-colored elements.                                                      | Text/icons on secondary buttons, accent elements with secondary color.                                  |

This table view provides a quick reference to ensure consistent and intuitive use of your app's color scheme across various components.
Here’s a detailed guide on which style to use for each typography in your `Typography` class, considering common use cases and design hierarchy in apps:

### 1. Display Styles
These styles are meant to grab attention and are typically used sparingly due to their size and prominence.

- **displayLarge**: Use this for very prominent headers, splash screens, or feature screens where you want to capture user attention.
- **displayMedium**: Ideal for secondary-level display headers, titles on important screens, or promotional banners.
- **displaySmall**: Great for sub-headers, featured elements on dashboards, or text that needs emphasis without dominating the UI.

### 2. Headline Styles
These styles are used for section headings or significant pieces of content that require more visual weight than body text.

- **headlineLarge**: Use for major section headers or titles on primary app screens.
- **headlineMedium**: Good for sub-sections within major screens or secondary headlines.
- **headlineSmall**: Use for tertiary headings or small content sections within screens, offering a structured hierarchy.

### 3. Title Styles
Titles are generally used for medium-emphasis text elements and shorter pieces of text.

- **titleLarge**: Best for top-level dialog titles, app bar titles, or card titles in larger containers.
- **titleMedium**: Suitable for secondary titles, section headers in lists, or key data titles.
- **titleSmall**: Useful for item titles in lists, subtitles, or small but meaningful text labels.

### 4. Body Styles
Body styles are designed for main content text and descriptions.

- **bodyLarge**: Use for main paragraphs, detailed descriptions, or important body text.
- **bodyMedium**: This is a great default for general content text such as descriptions and articles.
- **bodySmall**: Best for supporting text, disclaimers, or captions within the content.

### 5. Label Styles
Labels are used for smaller, less prominent text elements.

- **labelLarge**: Use for prominent labels, buttons, or input field labels that need some emphasis.
- **labelMedium**: Ideal for form labels, navigation text, or tags within the UI.
- **labelSmall**: Great for annotations, secondary captions, or small buttons.

### Example Use Cases:
| **Typography**     | **Recommended Use**                                                                                          |
|--------------------|-------------------------------------------------------------------------------------------------------------|
| **displayLarge**   | Large splash screens, home screen main titles                                                                |
| **displayMedium**  | Promotional headers, large UI sections                                                                      |
| **displaySmall**   | Sub-headers on dashboards, smaller promotional text                                                          |
| **headlineLarge**  | Main headers for screens, major sections                                                                     |
| **headlineMedium** | Sub-sections, secondary headers within major screens                                                         |
| **headlineSmall**  | Tertiary headings, content within cards or sub-sections                                                      |
| **titleLarge**     | App bar titles, top-level card titles                                                                        |
| **titleMedium**    | Section headers, titles for key UI elements                                                                  |
| **titleSmall**     | List item titles, subtitles, small section headers                                                           |
| **bodyLarge**      | Main content paragraphs, detailed descriptions                                                               |
| **bodyMedium**     | General content text                                                                                         |
| **bodySmall**      | Supporting content, annotations                                                                             |
| **labelLarge**     | Prominent button text, input field labels                                                                    |
| **labelMedium**    | Tags, navigation labels, form labels                                                                         |
| **labelSmall**     | Small annotations, secondary captions, helper text                                                          |

By following this guide, you ensure a clear hierarchy and consistency throughout your app's typography, improving readability and overall user experience.

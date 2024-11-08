# Adaptive Apps

- **Adaptive Apps**: Jetpack Compose allows creating flexible UIs for various screen sizes like phones, tablets, and foldables by using strategies like window size classes, adaptive UI components, and support for multiple input types.

- **Window Size Classes**: Categorize screen sizes into:
  - **Compact**: Small screens, often use single-column layouts.
  - **Medium**: Intermediate screens, may utilize two-column layouts.
  - **Expanded**: Large screens, suited for multi-pane and complex layouts.

This helps create responsive, user-friendly UIs across devices.


To develop an adaptive Android app using Jetpack Compose, follow these detailed steps to ensure your application provides an optimal user experience across various devices and screen sizes:

**1. Utilize Window Size Classes**

Window size classes categorize device screens into three types:

- **Compact**: Small screens, such as phones in portrait orientation.
- **Medium**: Medium-sized screens, like tablets or phones in landscape orientation.
- **Expanded**: Large screens, including tablets and desktops.

Implement these classes to adjust your app's layout accordingly.

**2. Implement Adaptive Layouts**

Design your UI to respond to different window size classes:

- **Compact**: Use single-column layouts to maximize space.
- **Medium**: Incorporate two-column layouts to utilize additional width effectively.
- **Expanded**: Employ multi-pane layouts to take full advantage of the available space.

Jetpack Compose's `Modifier` and `ConstraintLayout` can help create responsive designs.

**3. Leverage the Compose Material 3 Adaptive Library**

This library offers components that adapt to various screen sizes and orientations:

- **NavigationSuiteScaffold**: Automatically switches between navigation bar and navigation rail based on window size and device posture.
- **ListDetailPaneScaffold**: Implements a list-detail layout that adapts to different window sizes.

Integrate these components to simplify adaptive UI development.

**4. Support Diverse Input Methods**

Ensure your app accommodates various input devices:

- **Touch**: Design touch-friendly interfaces with appropriately sized touch targets.
- **Keyboard**: Implement keyboard navigation and shortcuts for efficiency.
- **Mouse and Trackpad**: Support hover states and right-click actions.
- **Stylus**: Enable precise input and pressure sensitivity where applicable.

Testing with these input methods ensures a comprehensive user experience.

**5. Test Across Multiple Devices and Configurations**

Thorough testing is crucial:

- **Emulators**: Use Android Studio's emulators to simulate different devices and screen sizes.
- **Physical Devices**: Test on actual hardware to assess performance and usability.
- **Configuration Changes**: Verify that your app handles orientation changes, multi-window modes, and foldable device postures gracefully.

Here's a concise summary suitable for a `README.md` file:

---

### Adaptive UI Dependencies for Jetpack Compose

To build adaptive user interfaces in Jetpack Compose, you can leverage the Material3 Adaptive library. Below is a summary of available dependencies and their purposes:

- **`adaptive`**: General-purpose adaptive components and utilities for creating flexible and responsive UIs.
  ```gradle
  implementation "androidx.compose.material3.adaptive:adaptive:1.1.0-alpha06"
  ```
  Use this for general adaptive UI features without focusing on specific components.

- **`adaptive-layout`**: Provides composables and tools for building adaptive layouts that dynamically adjust to different screen sizes and orientations.
  ```gradle
  implementation "androidx.compose.material3.adaptive:adaptive-layout:1.1.0-alpha06"
  ```
  Ideal for creating responsive layouts that adapt seamlessly across phones, tablets, and foldables.

- **`adaptive-navigation`**: Includes navigation components that adapt based on window size and device posture, such as navigation rails, bottom navigation, and drawers.
  ```gradle
  implementation "androidx.compose.material3.adaptive:adaptive-navigation:1.1.0-alpha06"
  ```
  Use this for making app navigation responsive and adaptable to various devices and orientations.

Combine these dependencies as needed to build a fully adaptive app experience.
## [Window size classes](https://developer.android.com/develop/ui/compose/building-adaptive-apps#window_size_classes)
Compute your app's WindowSizeClass using the currentWindowAdaptiveInfo() top‑level function of the Compose Material 3 Adaptive library. The function returns an instance of WindowAdaptiveInfo, which contains windowSizeClass. Your app receives updates whenever the window size class changes:
  ```kotlin
  val windowsClass = currentWindowAdaptiveInfo().windowSizeClass
val windowsPosture = currentWindowAdaptiveInfo().windowPosturec
  ```
### `currentWindowAdaptiveInfo()` Properties Overview

The `currentWindowAdaptiveInfo()` composable function provides two important properties to build adaptive UIs for different devices and screen configurations:

- **`windowSizeClass`**: Categorizes the window into logical sizes such as `Compact`, `Medium`, and `Expanded`. It helps you adapt layouts based on available screen space, like switching between single-column and multi-column views.
- **`windowPosture`**: Describes the physical posture or configuration of a device's screen (e.g., folded, flat, or half-open). This property is useful for adapting UIs for foldable devices and different form factors.

By combining `windowSizeClass` and `windowPosture`, you can create responsive and adaptive user interfaces that adjust based on screen size and device posture.

Here's a concise summary for your `README.md` file:

---

Here's the updated section for your `README.md` file with the link added:

---

### [Content Panes in Adaptive UI Design](https://developer.android.com/develop/ui/compose/building-adaptive-apps#content_panes)

**Content panes** enable displaying multiple content areas within a layout, optimizing space on larger screens such as tablets or foldables.

- **Terminology**: A "pane" represents an individual content area within a layout, differing from the traditional "screen" concept, which implies full device coverage.
- **Multi-Pane Layouts**: On expanded-width devices, multiple panes can be shown side-by-side, e.g., a list and its detailed view.
- **Adaptive Behavior**: 
  - **Compact/Medium Widths**: Display a single pane for primary content.
  - **Expanded Widths**: Show multiple panes, providing additional context.
- **Navigation**: 
  - **Compact/Medium**: Navigate between single panes.
  - **Expanded**: Update content in one pane without disrupting others.

Using content panes ensures responsive, user-friendly UIs across various screen sizes.


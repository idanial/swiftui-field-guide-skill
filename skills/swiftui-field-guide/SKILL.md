---
name: swiftui-field-guide
description: Build and review SwiftUI interactions using the SwiftUI Field Guide's patterns for motion, feedback, typography, adaptive layout, and accessibility. Use when implementing or improving these interface behaviors in an existing app.
---

# SwiftUI Field Guide

Apply the relevant lessons to the user's app and existing design. This is a focused interaction guide, not an app architecture guide or a workflow for maintaining the Field Guide gallery.

## Use the lessons

1. Inspect the affected views, deployment targets, and existing interaction. Choose the relevant lesson below and read only its reference, plus related accessibility guidance when needed.
2. For implementation, adapt the improved pattern with the smallest useful change. Prefer native APIs and remove unnecessary state, timers, or layout bookkeeping when the pattern replaces them.
3. For review, identify concrete behavior problems in the actual code, explain their user impact, and recommend minimal fixes with file locations. A different animation style alone is not a defect; do not force every lesson into every interface.
4. Validate the changed behavior using the target project's authorized build and test workflow. Report what was checked and any remaining limitations.

Preserve platform guards and deployment targets. Example comments describe the examples, not an exhaustive API availability table. Consult official Apple documentation when availability or behavior is uncertain; do not raise the deployment target just to apply a lesson.

Respect Reduce Motion, Dynamic Type, and meaningful accessibility labels. Preserve the intended state change when suppressing motion. Prefer system presentation behavior and verify accessibility implications when adapting transitions.

The complete examples retain demonstration inputs, reset controls, simulation toggles, sizing, and sample content for context. Adapt the interaction itself; do not copy demo scaffolding into production by default. Timings, scale values, and colors are illustrative. Preserve the app's visual language rather than imposing the gallery's layout or styling.

Distinguish these mechanisms: matched geometry connects views within a hierarchy; zoom transitions connect navigation or presentation sources and destinations; glass transitions morph nearby inline glass controls. They are not interchangeable.

## Lesson index

Read a reference when its title or APIs match the behavior being implemented or reviewed. For counters, consider both Numeric Motion and Numeric Widths; for constrained rows, Adaptive Layouts and Scaled Dimensions; for loading states, Loading Placeholders and Progress Animation. Use Glass Transitions for expanding inline actions, Toolbar Sheets for source-linked sheets, and Zoom Navigation for navigation destinations.

<!-- lessons:start -->

### Motion

- [Numeric Motion](references/changing-numbers.md) — `numericText(countsDown:)`, `contentTransition`
- [Spring Retargeting](references/responsive-springs.md) — `spring`, `withAnimation`, `completionCriteria`
- [Scoped Animations](references/scoped-animations.md) — `animation(_:body:)`, `scaleEffect`
- [Matched Geometry](references/matched-geometry.md) — `matchedGeometryEffect`, `@Namespace`
- [Phase Sequences](references/phase-sequences.md) — `phaseAnimator`, `Task`
- [Toolbar Sheets](references/toolbar-sheets.md) — `matchedTransitionSource`, `navigationTransition`, `popover`, `presentationCompactAdaptation`
- [Zoom Navigation](references/zoom-navigation.md) — `matchedTransitionSource`, `navigationTransition`, `zoom`
- [Stretchy Header](references/stretchy-header.md) — `visualEffect`, `GeometryProxy`, `scrollView`, `scaleEffect`
- [Symbol Drawing](references/drawing-symbols-on.md) — `symbolEffect(_:isActive:)`, `DrawOnSymbolEffect`, `symbolEffectsRemoved`
- [Blur Replace](references/blur-replace-transition.md) — `transition(_:)`, `blurReplace`, `BlurReplaceTransition`, `animation(_:value:)`
- [Glass Transitions](references/glass-transition-source.md) — `GlassEffectContainer`, `glassEffectID`, `glassEffectTransition`, `withAnimation`

### Feedback

- [Progress Animation](references/loading-completion.md) — `ProgressView`, `animation(_:value:)`
- [Symbol Replacement](references/symbol-changes.md) — `contentTransition`, `symbolEffect(.replace)`
- [Repeating Buttons](references/repeating-buttons.md) — `buttonRepeatBehavior`, `keyframeAnimator`, `accessibilityReduceMotion`
- [Press Feedback](references/button-press-feedback.md) — `ButtonStyle`, `isPressed`, `snappy`, `scaleEffect`
- [Loading Placeholders](references/placeholder-redaction.md) — `redacted(reason:)`, `RedactionReasons.placeholder`, `unredacted`, `redactionReasons`

### Typography

- [Numeric Widths](references/numeric-widths.md) — `monospacedDigit`

### Layout

- [Adaptive Layouts](references/flexible-content.md) — `ViewThatFits`, `HStack`, `VStack`
- [Concentric Corners](references/concentric-sheet-corners.md) — `ConcentricRectangle`, `containerShape`, `UICornerRadius`, `presentationCornerRadius`, `concentric(minimum:)`
- [Background Extension](references/background-extension.md) — `backgroundExtensionEffect`, `safeAreaPadding`, `NavigationSplitView`

### Accessibility

- [Scaled Dimensions](references/scaled-dimensions.md) — `@ScaledMetric`, `dynamicTypeSize`
- [Reduced Motion](references/reduced-motion.md) — `accessibilityReduceMotion`, `animation`

<!-- lessons:end -->

# ABCapp

CarouselListAppCompose is a feature-rich Android app built with Jetpack Compose that demonstrates modern UI patterns, reactive state management, and clean architecture. Designed as a learning resource or boilerplate, it combines a dynamic carousel with a filterable list and analytics—all wrapped in Material 3 design.

🔍 Core Concepts Implemented
1. Reactive UI with MVVM
StateFlow-driven UI: The CarouselListViewModel manages all business logic, exposing a CarouselListUiState stream to the composable screen.

Unidirectional data flow: User actions (swipes, searches) trigger state updates, which automatically recompose the UI.

2. Carousel & List Synergy
HorizontalPager: Smooth swipeable carousel using ExperimentalFoundationApi.

Live Data Binding: Changing the carousel page instantly updates the list below with page-specific items.

3. Advanced Composables
Sticky Headers: The search bar remains fixed while scrolling.

ModalBottomSheet: Statistics are calculated on-demand (e.g., character frequency analysis).

Custom Design System: Centralized Dimens.kt for consistent spacing, shapes, and elevations.

4. Search & Filtering
Debounced Search: Real-time filtering without external libraries.

Cross-Page Persistence: Each carousel page maintains its own search query and filtered results.

🏗️ Architecture Breakdown
kotlin
Copy
data class CarouselListUiState(  
    val pages: List<Page>,          // Carousel data  
    val currentPage: Int,           // Active page index  
    val currentPageItems: List<ListDisplayItem>,  // Filtered items  
    val searchQuery: String         // Search term  
)  
ViewModel: Handles data loading, pagination, search logic, and statistics.

Composables: Stateless UI components (e.g., CarouselItem, PagerIndicator) driven by state.

🛠️ Extensibility
Easily replace SampleData with:

Remote API calls (using Retrofit/Ktor)

Database persistence (Room)

Pagination (Paging 3 for large lists)

Add new analytics: Extend StatisticsData to include word counts, emoji trends, etc.

📚 Learning Takeaways
Jetpack Compose Best Practices:

Hoisting state to ViewModel.

Using LaunchedEffect for side effects (e.g., page change tracking).

Performance: Efficient list rendering with LazyColumn and keyed items.

Material 3 Theming: Customizable via MaterialTheme.colorScheme.

🚀 Potential Enhancements
Animations: Add transitions between carousel pages.

Testing: Write UI tests with ComposeTestRule and ViewModel unit tests.

Accessibility: Improve content descriptions and focus handling.
📂 Project Structure
Copy
com/example/carousellistappcompose/
├── ui/
│   ├── components/      # Reusable Composables (CarouselItem, PagerIndicator, etc.)
│   └── screen/         # Main screen logic
├── viewmodel/          # CarouselListViewModel (state management)
├── model/              # Data classes (Page, UiState, etc.)
└── Dimens.kt           # Centralized spacing/sizing constants
📝 Notes

📱 Screenshots
![Screenshot_20250410_114852_CarouselListApp](https://github.com/user-attachments/assets/217723bd-806b-4d06-82ea-7d851fed8921)
![Screenshot_20250410_114810_CarouselListApp](https://github.com/user-attachments/assets/859af223-5b92-4b55-b8e3-e9712e0704c4)
![Screenshot_20250410_114826_CarouselListApp](https://github.com/user-attachments/assets/930a0c1c-8438-43cb-8b36-0023b1c6906e)
![Screenshot_20250410_114932_CarouselListApp](https://github.com/user-attachments/assets/2b4c6845-3c2e-4938-b977-6c5ac4dd0c13)

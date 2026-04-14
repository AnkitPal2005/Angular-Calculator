# Design Document for Angular Calculator

## Component Architecture

The Angular Calculator is structured using the following main components:
- **AppComponent**: The root component that houses other components.
- **DisplayComponent**: Responsible for displaying the current number and results.
- **ButtonComponent**: A reusable component representing buttons for digits and operations.
- **HistoryComponent**: Displays the history of calculations.

## File Structure

The file structure of the Angular application is organized as follows:
```
angular-calculator/
├── src/
│   ├── app/
│   │   ├── components/
│   │   │   ├── display/
│   │   │   │   └── display.component.ts
│   │   │   ├── button/
│   │   │   │   └── button.component.ts
│   │   │   ├── history/
│   │   │   │   └── history.component.ts
│   │   │   └── app/
│   │   │       └── app.component.ts
│   │   └── services/
│   │       └── calculator.service.ts
│   └── index.html
└── main.ts
```

## Data Flow

The data flow in the Angular Calculator follows a unidirectional pattern:
1. **User Interaction**: User clicks buttons via `ButtonComponent`.
2. **Event Emission**: `ButtonComponent` emits events to `AppComponent`.
3. **State Update**: `AppComponent` updates the state based on received inputs.
4. **Display Update**: `DisplayComponent` receives the updated state and refreshes the display.
5. **History Management**: `AppComponent` calls `CalculatorService` to maintain the calculation history, which is displayed by `HistoryComponent`.
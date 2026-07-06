# Implementation Plan - Add Earnings Data and Tabbed Dashboard View

Add the missing stock tickers (AAPL, DOW) earnings data, integrate the earnings table as a separate tab inside the `Dashboard.js` component, and output the final table in HTML format.

## User Review Required

> [!IMPORTANT]
> The styling for the tabs will be added using vanilla CSS in `dashboard/src/styles.css` to maintain compatibility with the existing codebase (which does not use Tailwind CSS).

## Proposed Changes

### Dashboard Component and Styling

---

#### [MODIFY] [Earnings.js](file:///c:/prog/cygwin/home/samit_000/earnings_dashboard/dashboard/src/components/Earnings.js)
- Add AAPL and DOW to the `earningsLinks` mapping.
- Add AAPL and DOW row data to the `rows` array in alphabetical order.

#### [MODIFY] [Dashboard.js](file:///c:/prog/cygwin/home/samit_000/earnings_dashboard/dashboard/src/components/Dashboard.js)
- Import the `Earnings` component.
- Add state `activeTab` with choices `"patterns"` and `"earnings"`.
- Render a tab selection header at the top of the dashboard.
- Display the Technical Pattern Viewer content when `"patterns"` is active.
- Display the `Earnings` component when `"earnings"` is active.

#### [MODIFY] [styles.css](file:///c:/prog/cygwin/home/samit_000/earnings_dashboard/dashboard/src/styles.css)
- Add styling for the tab header (`.dashboard-tabs`) and tab buttons (`.tab-btn`, `.tab-btn.active`).

## Verification Plan

### Manual Verification
- Run the React development server using `npm start` and verify that:
  - The new tabs ("Technical Patterns" and "Earnings Summary") appear on the Technical Pattern Viewer page.
  - Clicking "Earnings Summary" shows the updated earnings table containing all 29 tickers in alphabetical order (including AAPL and DOW).
  - AAPL and DOW link to their respective investor relations web pages.
  - Color styling (green for Exceeded/Increasing, red for Missed/Reducing, etc.) functions correctly.

# pcf-universal-gantt-chart

## Interactive PCF Gantt Chart Control for Dynamics Grid and Canvas App

![example](https://github.com/MaTeMaTuK/pcf-universal-gantt-chart/blob/master/DocumentationAssets/ganttStandard.gif)

## Instruction

The solution is [here](https://github.com/MaTeMaTuK/pcf-universal-gantt-chart/releases) in assets

Quick guide for model driven app is [here](/Model%20Driven%20Guide.md)

Guide with details for canvas app is [here](/Canvas%20Guide.md)

## Configuration

| Parameter Name                                  | Description                                                                                                                    |
| :---------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------- |
| Title\*                                         | Specifies name on bar and list table.                                                                                          |
| Start Time\*                                    | Specifies start time display.                                                                                                  |
| End Time\*                                      | Specifies end time display.                                                                                                    |
| Progress                                        | Specifies progress display.                                                                                                    |
| Parent Record                                   | Specifies record dependency                                                                                                    |
| Task Type(Option)                               | Specifies record type. Task, milestone, project. You are able to configure option-text mapping in Task Type Mapping parameter. |
| Display Color(Option)                           | Specifies colors by option set value color.                                                                                    |
| Display Color(Text)                             | Specifies colors by hex color value.                                                                                           |
| Display Mode\*                                  | Enables or disables drag and drop feature.                                                                                     |
| IsSubgrid\*                                     | Specifies gantt as subgrid control.                                                                                            |
| Default Duration View\*                         | Specifies default duration display.                                                                                            |
| Task Type Mapping                               | Defines task type to option value                                                                                              |
| Display Date Format\*                           | Specifies date and time display format.                                                                                        |
| Time Step\*                                     | Specifies allowed step for move events. Sets in milliseconds.                                                                  |
| Font Size\*                                     | Specifies font size.                                                                                                           |
| Header Height\*                                 | Specifies header height.                                                                                                       |
| Row Height\*                                    | Specifies row height.                                                                                                          |
| List`s Cell Width\*                             | Specifies task list width. You may set 0 value for list hiding.                                                                |
| Column Width for Quarter of Day\*               | Specifies period width for Quarter of Day.                                                                                     |
| Column Width for Column Width for Half of Day\* | Specifies period width for Column Width for Half of Day.                                                                       |
| Column Width for Column Width for Day\*         | Specifies period width for Column Width for Day.                                                                               |
| Column Width for Column Width for Week\*        | Specifies period width for Column Width for Week.                                                                              |
| Column Width for Column Width for Month\*       | Specifies period width for Column Width for Month.                                                                             |
| Custom Display Name                             | Overrides display name.                                                                                                        |
| Custom Start Name                               | Overrides start time name.                                                                                                     |
| Custom End Name                                 | Overrides end time name.                                                                                                       |
| Custom Progress Name                            | Overrides progress name.                                                                                                       |
| Custom Progress Color                           | Specifies the taskbar progress fill color.                                                                                     |
| Custom Progress Selected Color                  | Specifies the taskbar progress fill color on select.                                                                           |
| Custom Background Color                         | Specifies the taskbar background fill color.                                                                                   |
| Custom Background Selected Color                | Specifies the taskbar background fill color on select.                                                                         |

\*Required

### Coloring

You are able to setup record coloring on base color or custom colors.
The base color gets from option set, text value or entity color. You can create base color for record palette [here](https://ant.design/docs/spec/colors#Palette-Generation-Tool).

Gantt takes from palette color #2 for background, #3 for selected background, #4 for progress color, #5 for selected progress color

Custom colors might be configured for overriding if you don't like color generation.

## Additional information

If you need your language you may contact with me or open an issue, where you may share your translations.

#### License GPLv3

#### Special thanks to [Aleksandra Daskevica](mailto:aleksandra.daskevica@cgi.com)

#### [Based on](https://github.com/MaTeMaTuK/gantt-task-react)


## Danish localization

This repository contains a Danish localization for the PCF Universal Gantt Chart control. The translated resource file is:

- `UniversalGanttChartComponent/strings/UniversalGanttChartComponent.1033.resx` — Danish translations used by the PCF control via the control manifest and `context.resources.getString(...)` calls.

If you add more translations, add a `.resx` file into the `UniversalGanttChartComponent/strings/` folder and reference it in `UniversalGanttChartComponent/ControlManifest.Input.xml` if necessary.

## Continuous Integration (GitHub Actions)

This repository includes a GitHub Actions workflow that installs dependencies and runs the configured `build` script (if present) in the repository and in common sub-projects. The workflow lives at `.github/workflows/ci.yml` and runs on push and pull requests.

It will:

- Checkout the repository
- Install Node (LTS) using `actions/setup-node`
- Run `npm ci` and `npm run build` in any of these locations if they contain a `package.json`:
  - repository root
  - `gantt-solution`
  - `pcf-universal-gantt-chart-master`

If you prefer a different Node version or want the workflow to run only for a single subproject, edit `.github/workflows/ci.yml` accordingly.

## Removing large archives

The repository previously contained a ZIP archive of the project tree (`pcf-universal-gantt-chart-master.zip`). That file has been removed from the repository to keep history and clones small — the project sources are already present in the repository as a folder.

## How to build locally (Windows / PowerShell)

Open a PowerShell at the repository root and run the following for the PCF project folder you want to build. Replace `<folder>` with either `.` (root), `gantt-solution`, or `pcf-universal-gantt-chart-master` depending on where you want to build.

```powershell
Set-Location -Path .\\pcf-universal-gantt-chart-master
npm ci
npm run build
```

Notes:
- PCF projects typically use `pcf-scripts` and `npm run build` will compile TypeScript and produce `out/controls` artifacts.
- If you plan to publish the control as a managed solution, use the `.pcfproj`/`.cdsproj` files and MSBuild tooling described in the original project documentation.

---

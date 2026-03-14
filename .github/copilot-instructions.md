# Copilot Workspace Instructions

## 🚀 MANDATORY Development Checklist

Before committing ANY changes, ensure ALL items pass:

- [ ] **Lint**: Code follows C# conventions (PascalCase public, camelCase private, no unused usings)
- [ ] **Build**: `dotnet build SocOps/SocOps.csproj` passes with zero errors
- [ ] **Test**: Manual testing - verify affected features work in browser

## Project Overview

**SocOps** - Social Bingo game (Blazor WebAssembly .NET 10). Players mark squares by finding people matching bingo questions, aiming for 5-in-a-row. Workshop project for AI-assisted development.

**Architecture**: Components (UI) → Services (logic) → Models (data)
- `Components/` - BingoBoard, BingoSquare, GameScreen, etc.
- `Services/` - BingoGameService (state), BingoLogicService (logic)  
- `Models/` - GameState, BingoSquareData
- `Data/` - Questions.cs (bingo prompts)

## Essential Commands
```bash
dotnet build SocOps/SocOps.csproj    # Build
dotnet run --project SocOps          # Run (http://localhost:5166)
```

## Code Patterns

**Components**: `ComponentName.razor` + `ComponentName.razor.css`
- Use `[Parameter]` for inputs, `EventCallback` for events
- Services handle state, components handle presentation

**Services**: Register in Program.cs, use DI
- BingoGameService: state management  
- BingoLogicService: pure game logic

**Styling**: Component-scoped `.razor.css`, utilities in `wwwroot/css/app.css`

## Critical Notes
- Static assets → `wwwroot/` only
- No test project exists - use manual testing
- `.razor.css` required for style isolation
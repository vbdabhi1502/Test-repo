Repository Architecture Guidelines & Coding Standards
1. Backend Standards (.NET Core Web API)
Architecture: Clean Architecture pattern (Controllers -> Application/Services -> Domain/Repositories).
Error Handling: Never catch generic `Exception` inside Controllers or Services without re-throwing. Use global exception handling middleware returning `ProblemDetails`.
Entity Framework Core: Always use asynchronous EF Core queries (`ToListAsync`, `FirstOrDefaultAsync`) with cancellation tokens. Avoid `.Result` or `.Wait()`.
Validation: Enforce FluentValidation for incoming command/query DTOs.
2. Frontend Standards (Angular)
Component Architecture: Standalone components only (`standalone: true`).
State & Reactivity: Use Signals (`signal()`, `computed()`) for component reactivity. Avoid manual subscriptions in templates without `async` pipe or `takeUntilDestroyed()`.
Type Safety: Strict TypeScript mode enabled; explicitly avoid `any`.
3. Pull Request Requirements
Any automated fix must include comments citing the architectural pattern followed.

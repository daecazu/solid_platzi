# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python project focused on demonstrating SOLID principles. The main codebase consists of a single payment processing system (`initial_code.py`) that serves as a starting point for refactoring exercises to apply SOLID design principles.

## Code Architecture

The current architecture is intentionally monolithic and violates several SOLID principles:

- **Single Responsibility Principle**: The `PaymentProcessor` class handles payment processing, validation, email/SMS notifications, and logging
- **Open/Closed Principle**: Adding new payment methods or notification channels requires modifying existing code
- **Dependency Inversion**: Direct dependencies on external services (Stripe, email, SMS) are hardcoded

The `PaymentProcessor.process_transaction()` method in `initial_code.py:8-66` contains all business logic and should be the primary target for refactoring exercises.

## Development Environment

This project uses Python with the following dependencies:
- `stripe` - Payment processing
- `python-dotenv` - Environment variable management

Environment variables expected:
- `STRIPE_API_KEY` - Stripe API key for payment processing

## Development Setup

Create and activate virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## Running the Code

Execute the main script:
```bash
source venv/bin/activate  # Activate virtual environment first
python initial_code.py
```

The script demonstrates payment processing with both email and phone notification examples.

## Key Files

- `initial_code.py` - Main payment processor implementation that violates SOLID principles
- `transactions.log` - Generated log file for payment records (created at runtime)

## Python 3.12 Type Hints Standards

When working with Python code in this repository, follow these strict type hinting conventions:

### Generic Types
- Use built-in generic types: `list[str]`, `dict[str, int]`, `set[int]`
- Avoid `typing.List`, `typing.Dict`, `typing.Set` (deprecated in 3.12)
- For complex generics: `dict[str, list[int]]`, `list[dict[str, Any]]`

### Type Aliases and Union Types
- Use `type` keyword for type aliases: `type UserId = int`
- Use `|` syntax for unions: `str | int | None` instead of `Union[str, int, None]`
- Use `X | None` instead of `Optional[X]`

### Function Signatures
- Always annotate function parameters and return types
- Use `-> None` for functions that don't return values
- Example: `def process_payment(amount: int, source: str) -> dict[str, Any]:`

### Class Attributes and Methods
- Annotate class attributes using the new syntax
- Use `Self` from `typing` for methods returning the instance
- Example: `def configure(self) -> Self:`

### Protocol and ABC Usage
- Prefer `Protocol` for structural typing over abstract base classes when possible
- Use `@abstractmethod` with clear type annotations

### Literal and Final
- Use `Literal` for string/int constants: `Literal["success", "failed"]`
- Use `Final` for constants: `API_VERSION: Final[str] = "v1"`

### Required Rules
1. All new functions must have complete type annotations
2. All class methods must have typed parameters and return types
3. Use modern Python 3.12 syntax (no legacy `typing` imports when built-ins exist)
4. Prefer explicit over implicit types
5. Use `Any` sparingly and document why when used

## Git Commit Guidelines

- **NEVER** reference Claude Code or AI assistance in commit messages
- Write commit messages as if they were written by a human developer
- Focus on the technical changes and business value
- Use conventional commit format when possible: `feat:`, `fix:`, `refactor:`, etc.
- Example: `refactor: extract payment validation into separate class` instead of `refactor: apply SOLID principles with Claude Code assistance`

## Refactoring Approach

When applying SOLID principles, consider:
1. Extracting separate classes for validation, payment processing, notifications, and logging
2. Creating interfaces/abstract base classes for payment processors and notification services
3. Implementing dependency injection for external service dependencies
4. Separating concerns to make each class have a single responsibility
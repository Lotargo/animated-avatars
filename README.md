# The Living Bunker: Semiotic Experiment

<div align="center">

![Status](https://img.shields.io/badge/status-active%20prototype-F39C12?style=flat-square)
![Type](https://img.shields.io/badge/type-research%20sandbox-9B59B6?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

</div>

**Living Bunker** is an autonomous multi-agent simulation for exploring AI semiotics, role-based social behavior, non-verbal communication, and emergent coordination in a confined environment.

It features 3 human residents and **Luna**, a sentient AI cat who communicates solely through "Meow" but perceives layers of reality hidden from the others.

![Bunker Visualization](docs/screenshots/bunker_overview.png)

## Status and Positioning

This repository is an **active research prototype**, not a finished game and not a polished entertainment product.

The visual interface exists primarily as an **observability and control layer**: it makes agent state, spatial context, anomalies, scripted scenarios, and emergent social behavior easier to inspect. The goal is not to build "a bunker game" first. The goal is to test how multiple AI agents behave when they are placed into a shared world, given roles, constrained by asymmetric information, and exposed to repeatable automated scenarios.

In its current form, the project validates basic mechanics: autonomous residents, role separation, compressed communication, invisible threats, scenario triggers, procedural assets, and an Architect console for controlled experiments. Many systems are still evolving, and the project should be read as a sandbox for AI-society experiments rather than a completed product.

## Key Features

*   **AI Society Sandbox:** Multiple AI-controlled agents can be placed into a shared environment, assigned roles, and observed as they react to each other and to scripted world events.
*   **Autonomous Agents:** Powered by **Groq** and **Cerebras** LLMs (Llama 3.1/3.3).
*   **The "Semiotic Alien":** Luna (The Cat) understands the world perfectly but is constrained to communicate only via "Meow", forcing other agents (and the LLM itself) to encode meaning into rhythm and punctuation.
*   **Invisible Threats:** Anomalies (Ghosts, Doppelgängers) "gestate" invisibly. Only the cat can see them forming, acting as a living Geiger counter.
*   **Doppelgänger Mechanic:** A shapeshifting entity that mimics the cat to deceive residents, but is destroyed by the presence of the real cat.
*   **Scenario Automation:** The Architect console can launch repeatable local scenarios for testing agent behavior under controlled conditions.
*   **Observability-first Interface:** The browser UI is a debugging and inspection surface for the simulation, not the main research contribution.
*   **Procedural Assets:** All graphics are generated programmatically using Python (`scripts/generate_assets.py`).

## Quick Start

### One-click-ish launcher

On Windows, run:
```bash
launch.bat
```

Or from any shell:
```bash
python launch.py
```

The launcher installs/checks dependencies, builds TypeScript, generates missing assets, starts Flask, and opens the browser. If no API keys are configured, it enables demo mode automatically.

### Manual start

1.  **Install:**
    ```bash
    pip install -r requirements.txt
    ```
2.  **Configure API Keys:**
    ```bash
    export GROQ_API_KEY="your_key"
    export CEREBRAS_API_KEY="your_key"
    ```
    Or run without keys in demo mode:
    ```bash
    export LIVING_BUNKER_DEMO=1
    ```
3.  **Generate Assets:**
    ```bash
    python scripts/generate_assets.py
    ```
4.  **Run:**
    ```bash
    python app.py
    ```
5.  **View:** Open `http://localhost:5000`.

## Documentation

*   [Setup & Installation](docs/setup.md)
*   [Working Map](docs/working_map.md)
*   [Active Sprint](docs/sprint.md)
*   [Runtime Contracts](docs/contracts.md)
*   [Architecture Overview](docs/architecture.md)
*   [Known Issues](docs/known_issues.md)
*   [Agents & Luna (The Cat)](docs/agents.md)
*   [Anomalies & Atmosphere](docs/anomalies.md)
*   [Architect Mode (God Console)](docs/architect_mode.md)

## Repository Layout

*   `app.py` / `launch.py`: simple pip-friendly entry points.
*   `bunker/`: Flask-adjacent backend logic, LLM orchestration, runtime settings, and demo mode.
*   `scripts/`: one-off utility scripts for assets, model checks, graphics, and manual verification.
*   `static/`: browser simulation, TypeScript sources, CSS, data, and generated game bundle.
*   `generators/`: procedural asset generation library used by `scripts/generate_assets.py`.
*   `tests/`: Python and Node test coverage.

## Local Scenarios

From the Architect console, you can run repeatable local scenarios:

```txt
/scenario first_ghost
/scenario luna_warning_ignored
```

## The Experiment

The core question of this project is broader than whether a small game-like simulation can run. The experiment asks: **How do AI agents form shared meaning, warnings, trust, and social behavior when placed inside a persistent environment with roles, asymmetric perception, and constrained communication channels?**

One focused sub-question is: *Can an LLM maintain a coherent internal state and strategy when its output channel is aggressively compressed (to just "Meow")?*

Early results show that Luna successfully uses "Staring" and specific vocalizations to alert other agents to invisible threats, creating a rudimentary shared culture where "Cat staring at wall" = "Danger".

## License

MIT
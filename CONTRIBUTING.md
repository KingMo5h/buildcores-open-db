# Contributing to BuildCores OpenDB

Thank you for your interest in contributing to BuildCores OpenDB! This document provides guidelines and instructions for contributing.

## Getting Started


### Types of Contributions

- Adding new PC components
- Updating existing component information
- Correcting errors in component data
- Improving schemas for better validation

### Adding a New Component

1. Identify the appropriate category folder in `/open-db/` (e.g., CPU, GPU, RAM)
2. Create a new JSON file in that folder
   - You must generate a UUID v4 for the new component
   - Use this UUID as both the filename (e.g., `12345678-1234-5678-1234-567812345678.json`) and in the `opendb_id` field within the JSON content
   - The API requires this UUID and will not auto-assign one
3. Populate the JSON file according to the appropriate schema in `/schemas/`
4. Make sure all required fields are included

### Updating an Existing Component

1. Find the component's JSON file in the appropriate category folder
2. Make the necessary changes while maintaining schema compliance
3. Do not change the `opendb_id` field as this is the unique identifier

### Data Quality Guidelines

- Use consistent naming conventions for similar components
- Provide accurate specifications based on manufacturer documentation
- Include retailer SKUs and links when available
- Ensure all measurements use the correct units as specified in the schema
- Fill in as many fields as possible, not just the required ones

## Validation

### Local Validation

Before opening a pull request, you can validate your JSON files locally. This
repository uses [`ajv-cli`](https://github.com/ajv-validator/ajv-cli) for schema
validation.

1. **Install Node.js and npm** if you don't already have them. Any recent LTS
   version (16 or newer) works.
2. **Install ajv-cli** globally (or use it via `npx`):
   ```bash
   npm install -g ajv-cli
   ```
3. **Run validation**. Point `ajv` to the appropriate schema and data files. For
   example, to validate all CPU JSON files:
   ```bash
   ajv validate -s schemas/CPU.schema.json -d open-db/CPU/*.json --all-errors
   ```
   Replace `CPU` with other categories as needed, or provide a specific file
   path:
   ```bash
   ajv validate -s schemas/<category>.schema.json -d open-db/<category>/<file>.json --all-errors
   ```
4. Ensure the filename matches the `opendb_id` field inside each JSON file.

Fix any validation errors before submitting your PR.

### PR Validation

When you submit a PR:

1. GitHub Actions will automatically validate your changes
2. The validation results will be posted as a comment on your PR
3. If validation fails, you'll need to fix the issues before merging

## Submitting Changes

1. Commit your changes with a descriptive message
   ```
   git commit -am "Add Intel Core i9-14900K CPU"
   ```
2. Push to your fork
   ```
   git push origin your-feature-branch
   ```
3. Submit a pull request to the main repository
4. In your PR description:
   - Explain what your changes do
   - Reference any related issues
   - Note the source of your data if applicable
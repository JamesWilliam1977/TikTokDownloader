```markdown
# TikTokDownloader Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the development patterns, coding conventions, and workflows used in the TikTokDownloader Python repository. You'll learn how to structure code, write commits, manage dependencies, and contribute tests in a way that's consistent with the project's standards.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `video_downloader.py`, `tiktok_utils.py`

### Import Style
- Use **relative imports** within the package.
  - Example:
    ```python
    from .utils import download_video
    ```

### Export Style
- Use **named exports** (explicitly define what is exported).
  - Example:
    ```python
    __all__ = ["download_video", "parse_url"]
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use prefixes like `build`, `chore`.
- Keep commit messages concise (average ~53 characters).
  - Example:
    ```
    chore: update requirements for security patch
    build: bump requests to 2.28.0
    ```

## Workflows

### Dependency Update
**Trigger:** When a dependency needs to be updated (often via Dependabot).
**Command:** `/update-dependency`

1. Update the dependency version in `pyproject.toml`.
2. Update the dependency version in `requirements.txt`.
3. Update the lockfile `uv.lock`.
4. Commit the changes with a message indicating the dependency and new version.
   - Example commit message:
     ```
     chore: update requests to 2.28.0
     ```

#### Example
```bash
# 1. Edit pyproject.toml and requirements.txt to bump the version
# 2. Regenerate lockfile
uv pip compile

# 3. Commit changes
git add pyproject.toml requirements.txt uv.lock
git commit -m "chore: update requests to 2.28.0"
git push
```

## Testing Patterns

- Test files follow the `*.test.*` naming pattern.
  - Example: `downloader.test.py`
- The testing framework is **unknown**, so check existing test files for structure.
- Place tests alongside the modules they test or in a dedicated `tests/` directory.

#### Example Test File
```python
# downloader.test.py

def test_download_video():
    # Arrange
    url = "https://www.tiktok.com/@user/video/123456"
    # Act
    result = download_video(url)
    # Assert
    assert result is not None
```

## Commands

| Command            | Purpose                                       |
|--------------------|-----------------------------------------------|
| /update-dependency | Update one or more dependencies to new version|
```

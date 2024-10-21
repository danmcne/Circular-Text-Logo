# Circular Text Logo Generator

## Overview

This LaTeX project allows you to generate circular text logos with customizable text, fonts, colors, and line styles. It leverages `PSTricks` and `pst-text` to create text paths that follow circular arcs, making it suitable for creating logos or signs with top, bottom, and center-aligned text. The project also supports the use of specialized fonts such as runes and math blackboard bold, offering flexibility for creative designs.

## Features

- **Top Arc Text**: Custom text at the top of the circle, with options for color, font style, and orientation correction (to ensure text is displayed correctly on the outer edge of the circle).
- **Bottom Arc Text**: Customizable text on the bottom arc of the circle, supporting color changes and font options.
- **Center Text**: Main text in the center of the circle, supporting multiple lines, bold or italic styles, and special fonts like `mathbb`.
- **Supports Runes**: Using the `allrunes` package, you can display runic characters in the top or bottom arc of the circle.

## Dependencies

To compile the document, you'll need the following LaTeX packages:

- `pstricks`
- `pst-text`
- `amssymb`
- `graphicx`
- `allrunes`

Make sure these packages are installed in your LaTeX environment.

## How to Use

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/circular-text-logo-generator.git
   cd circular-text-logo-generator
   ```

2. **Edit the LaTeX File**:
   Open the `.tex` file and modify the following sections to customize the logo:

   - **Top Text**: Update the `Top Text \textara{also}~\textara{in}~\textara{runes}` section to your desired text, including runes if needed.
   - **Bottom Text**: Modify the `\mathbb{THIS~IS~THE~BOTTOM~TEXT}` to change the bottom text. You can use different fonts or math symbols here.
   - **Center Text**: Customize the `CENTER~TEXT` and additional lines in the center of the logo.

3. **Compile the Document**:
   Use a LaTeX compiler that supports `PSTricks`, such as `XeLaTeX` or `LaTeX -> dvips -> ps2pdf` (the second is preferred):

   ```bash
   xelatex circular_text_logo.tex
   ```

4. **Output**:
   After compilation, the generated PDF will contain your circular text logo.

## Example

Here’s what a typical circular text logo looks like:

- **Top Arc**: Red, bold text with runes at the top of the circle.
- **Bottom Arc**: Purple text in math blackboard bold at the bottom.
- **Center Text**: Large, centered text in blackboard bold, with additional italicized lines.

![Example Logo](example.png)

## Customization

- **Font Customization**: You can change the fonts for both the top and bottom text. For example, use `\mathbb{}` for math blackboard bold, or add runes with `\textara{}`.
- **Color Customization**: Adjust the `\textcolor{}` command to use different colors for each section of text.
- **Line Thickness**: Modify the `linewidth` in the `\psarc` commands to adjust the thickness of the circle lines.

## License

This project is licensed under the MIT License. Feel free to modify and share!

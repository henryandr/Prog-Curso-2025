# Instrucciones de Compilación

## Logo Requerido

Los archivos de examen requieren un logo de la Universidad Pontificia Bolivariana. El archivo debe llamarse `LogoUPB.jpg` y colocarse en el directorio `Examenes/`.

### Opciones si no tiene el logo:

1. **Obtener el logo oficial:** Solicite el logo a la Universidad Pontificia Bolivariana
2. **Comentar las líneas del logo:** Modifique los archivos .tex comentando las líneas que incluyen el logo:

```latex
% En la sección del título, comente esta línea:
% \multirow{5}{*}{\includegraphics[width=1\linewidth]{LogoUPB.jpg}}
```

3. **Usar un logo temporal:** Cree o descargue una imagen placeholder con el nombre `LogoUPB.jpg`

## Compilación con pdfLaTeX

Una vez que tenga el logo o haya comentado las líneas correspondientes:

### Linux/Mac

```bash
cd Examenes
pdflatex Parcial_A.tex
pdflatex Parcial_B.tex
pdflatex Parcial_C.tex
pdflatex Parcial_D.tex
```

### Windows (Command Prompt)

```cmd
cd Examenes
pdflatex Parcial_A.tex
pdflatex Parcial_B.tex
pdflatex Parcial_C.tex
pdflatex Parcial_D.tex
```

### Windows (PowerShell)

```powershell
cd Examenes
pdflatex Parcial_A.tex
pdflatex Parcial_B.tex
pdflatex Parcial_C.tex
pdflatex Parcial_D.tex
```

## Instalación de LaTeX

Si no tiene LaTeX instalado:

### Ubuntu/Debian

```bash
sudo apt-get update
sudo apt-get install texlive-full
```

### macOS (con Homebrew)

```bash
brew install --cask mactex
```

### Windows

Descargue e instale MiKTeX desde: https://miktex.org/download

## Paquetes Requeridos

Los exámenes usan los siguientes paquetes de LaTeX:

- exam
- inputenc
- graphicx
- tcolorbox
- stfloats
- multirow
- array
- vhistory
- verbatim
- multicol, caption, capt-of
- enumitem
- microtype
- geometry
- fancyhdr
- listings
- xcolor

Estos paquetes suelen estar incluidos en instalaciones completas de LaTeX como texlive-full o MiKTeX.

## Compilación en Overleaf

Si prefiere usar Overleaf (servicio en línea):

1. Cree un nuevo proyecto en Overleaf
2. Suba los archivos .tex
3. Suba el logo LogoUPB.jpg o comente las líneas correspondientes
4. Compile con pdfLaTeX

## Archivos Generados

La compilación generará:

- `Parcial_A.pdf`
- `Parcial_B.pdf`
- `Parcial_C.pdf`
- `Parcial_D.pdf`

Además de archivos auxiliares (.aux, .log, etc.) que pueden ser eliminados después de la compilación.

## Limpieza de Archivos Auxiliares

Después de compilar, puede eliminar los archivos auxiliares:

### Linux/Mac

```bash
rm *.aux *.log *.out
```

### Windows

```cmd
del *.aux *.log *.out
```

## Solución de Problemas

### Error: File 'LogoUPB.jpg' not found

**Solución:** Proporcione el archivo de logo o comente las líneas que lo incluyen.

### Error: Package not found

**Solución:** Instale el paquete faltante o use una distribución completa de LaTeX.

### La tabla de puntos no aparece correctamente

**Solución:** Compile dos veces. La primera compilación genera las referencias, la segunda las resuelve.

### Caracteres especiales no se muestran correctamente

**Solución:** Asegúrese de que sus archivos .tex estén guardados con codificación UTF-8.

## Contacto

Para problemas técnicos con la compilación, consulte la documentación de LaTeX o los foros de la comunidad TeX.

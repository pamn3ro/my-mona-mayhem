<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematización orientada al diseño

---

En esta parte, usarás los ciclos de planificación e implementación de Copilot para diseñar una transformación completa del tema. Este es un desarrollo orientado al diseño: empieza con una visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el tema retro

<!-- track:vscode:start -->
Cambia al modo **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar el modo de planificación.
<!-- track:cli:end -->

Escribe este prompt:

> Quiero transformar esta página en una experiencia completa de arcade retro. Planifica una renovación visual que incluya: efectos de líneas de barrido CRT en el fondo, un brillo de neón pulsante en el título, una insignia VS animada con cambios de degradado, una capa de brillo sobre las tarjetas de resultados de usuarios, animaciones de entrada flotante para los campos de entrada, texto de carga que cambie entre verde y morado, y efectos de brillo al pasar el cursor sobre los cuadros de contribuciones. Mantén el fondo oscuro (`#0a0a1a`) y usa verde (`#5fed83`) y morado (`#8a2be2`) como colores de acento. Usa un tema oscuro con la tipografía retro Press Start 2P de Google Fonts.

Copilot generará un plan detallado que abarque todos los efectos visuales. **No lo aceptes de inmediato**: revisa el plan e itera:

- Sugiere ajustes al ritmo de las animaciones (por ejemplo: «Haz que el pulso de neón sea más lento, de unos 3 segundos»).
- Pregunta por efectos concretos (por ejemplo: «¿Cómo funcionará la capa de brillo sobre las tarjetas?»).
- Pide cambios en el enfoque si algo no te convence.

## Tarea 2: Implementa el tema

Cuando estés conforme con el plan, pide a Copilot que lo implemente.

> Implementa el plan de tema retro arcade que acabamos de diseñar.

Copilot añadirá varias animaciones CSS, pseudoelementos y transiciones en la hoja de estilos. Por ejemplo:

- `@keyframes` para líneas de barrido, pulsos de neón, destellos y efectos de entrada flotante.
- Pseudoelementos (`::before`, `::after`) para los efectos de superposición.
- Propiedades personalizadas de CSS para los colores del tema.
- Transiciones y estados al pasar el cursor sobre los elementos interactivos.

<!-- track:cli:start -->
Cuando se apliquen los cambios, usa `/diff` para revisar los estilos antes de aprobarlos.
<!-- track:cli:end -->

## Tarea 3: Ajusta el estilo

> **⚠️ ¿No ves los cambios?** Si el nuevo tema o las animaciones no aparecen, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y fuerza la actualización (`Ctrl+Shift+R`) del navegador.

Mantén abierta la vista previa en el navegador e itera sobre el diseño. Prueba prompts como estos:

> El efecto de líneas de barrido es demasiado intenso; reduce la opacidad a 0.03.

> Añade un sutil parpadeo eléctrico al texto del título.

> La insignia VS debería pulsar con más intensidad.

Esto es **desarrollo orientado al diseño**: iteras sobre el resultado visual en tiempo real. Cada prompt refina la experiencia hasta que te convenza. No te conformes con algo «suficientemente bueno»: sigue ajustando el estilo hasta que la página parezca parte de una máquina recreativa.

## Tarea 4: Actualiza las instrucciones

Las instrucciones deben reflejar las decisiones de diseño importantes para que los prompts posteriores mantengan la coherencia.

<!-- track:vscode:start -->
Pide a Copilot Chat:

> Añade a `copilot-instructions.md` una sección de guía de diseño que describa el tema retro arcade: colores, tipografías y estilo de animación.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:

> Actualiza las instrucciones del repositorio con una breve guía de diseño para el tema retro arcade: colores, tipografías, estilo de animación y la regla de que la nueva interfaz debe mantener la estética de neón.
<!-- track:cli:end -->

Cuando la página se vea bien, haz commit de las instrucciones y los cambios de diseño.

## ✅ Parte 4 completada

**Lo que has aprendido:**

- Usar flujos de planificación para definir un **sistema de diseño antes de implementarlo**.
- **Iterar sobre el resultado visual** con prompts de seguimiento.
- **Actualizar las instrucciones tras tomar decisiones importantes** para mantener la identidad visual.

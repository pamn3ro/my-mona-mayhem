<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Construye el juego con flujos de trabajo agénticos

---

En esta parte, Copilot pasa de planificar a implementar. En lugar de escribir código línea por línea, describes lo que quieres y dejas que Copilot trabaje en los archivos necesarios.

## Tarea 1: Conecta la batalla

<!-- track:vscode:start -->
1. Cambia al modo **Agent** en Copilot Chat.
2. Escribe este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Vuelve al flujo de programación estándar de Copilot CLI (o mantén el modo autopilot si quieres que Copilot continúe hasta que lo detengas).
2. Si te resulta útil, menciona el archivo de la página para dar más contexto: `@src/pages/index.astro`.
3. Escribe este prompt:
<!-- track:cli:end -->

   > Añade JavaScript del lado del cliente a la página de batalla para que:
   > 1. Al hacer clic en el botón Battle, obtenga los dos nombres de usuario de los campos.
   > 2. Compruebe que ambos estén rellenados (muestra un error si no lo están).
   > 3. Obtenga en paralelo, desde nuestra API, los datos de contribuciones de ambos usuarios.
   > 4. Muestre gráficos de contribuciones como cuadrículas de cuadros de colores; cada día debe ser un cuadro que use la paleta de colores de GitHub.
   > 5. Muestre una insignia VS entre ambos usuarios.
   > 6. Muestre el nombre de usuario, el total de contribuciones y el intervalo de fechas de cada usuario.
   > 7. Gestione los estados de carga y los errores.
   > 8. También active la acción al pulsar Enter en los campos.
   > 9. Por ahora, usa la interfaz sencilla que ya está creada.
   >
   > Usa interfaces de TypeScript para la estructura de datos de contribuciones.

<!-- track:vscode:start -->
3. Deja que Agent Mode implemente los cambios en `index.astro`.
4. Revisa los cambios propuestos en la vista de diferencias antes de aceptarlos.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deja que Copilot CLI trabaje en `src/pages/index.astro`.
5. Usa `/diff` para revisar los cambios generados y luego apruébalos.
<!-- track:cli:end -->

## Tarea 2: Prueba la batalla

> **⚠️ ¿No ves los cambios?** Si la página de batalla no se actualizó, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y actualiza el navegador.

1. Introduce `octocat` y `torvalds` como nombres de usuario y haz clic en **Battle**.
2. Deberías ver los dos gráficos de contribuciones uno junto al otro, con cuadrículas de cuadros de colores.
3. Prueba los casos de error:
   - Deja vacío uno o ambos campos y haz clic en Battle: debería aparecer un error de validación.
   - Introduce un nombre de usuario no válido: la aplicación debería mostrar un error de la API.
4. Pulsa **Enter** en cualquiera de los campos: debería iniciar la batalla igual que al hacer clic en el botón.

## Tarea 3: Itera con Copilot

Si algo no está del todo bien, envía comentarios de seguimiento a Copilot. Por ejemplo:

- *«Los cuadros de contribuciones son demasiado grandes; cámbialos a 12 × 12 px»*
- *«Añade una descripción emergente al pasar el cursor que muestre la fecha y el número de contribuciones»*
- *«El estado de carga necesita una animación de pulso»*

<!-- track:vscode:start -->
Agent Mode gestiona de forma natural los cambios en varios archivos y las iteraciones. Cada prompt de seguimiento aprovecha la conversación anterior, así que puedes refinar la implementación poco a poco sin empezar de nuevo.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Las sesiones de Copilot CLI conservan el historial, por lo que cada seguimiento se basa en los anteriores. Usa `/session` o `/context` para inspeccionar el contexto que Copilot mantiene, y `/review` después de una iteración grande para buscar errores o mejoras.
<!-- track:cli:end -->

## Consejos para esta parte

- **Especifica lo que quieres**: los requisitos claros producen mejores resultados.
- **Divide las tareas grandes en prompts más pequeños** si Copilot se desvía.
- **Revisa los cambios antes de aceptarlos**: inspeccionar el diff es más rápido que reescribir después.
- **Prueba la aplicación justo después de cada implementación** para localizar los problemas.

## ✅ Parte 3 completada

Has aprendido a:

- Usar Copilot para **implementar funcionalidades en varios archivos**.
- **Iterar sobre los resultados** con comentarios de seguimiento concretos.
- Gestionar el **ciclo completo de una funcionalidad**: implementación, revisión, pruebas y refinamiento.

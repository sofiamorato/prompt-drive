# Registro de uso de IA

**Asistentes usados** (ChatGPT, Claude, Gemini, Copilot, otros) y para qué (ideas, redacción del prompt, análisis de fallos, casos de prueba, video):

Claude Code (en VS Code): escribir `handover.js`, compilar y comprobar el bundle, probar la lógica con un navegador controlado por script, diagnosticar la caché del navegador, redactar la nota de diseño, el guion y la presentación del video, y llevar el registro de errores.

**Tres prompts que me sirvieron** (pégalos o resúmelos, y di qué salió de cada uno):

1. Un prompt largo con el diseño ya decidido (borde violeta, pastilla AUTO/MANUAL, tiempos, reglas duras como no escribir en `VehicleState` ni editar bundles a mano, y qué leer y en qué orden). Salió una feature en un solo archivo que compiló a la primera.
2. "¿No lo puedes probar tú?" Salió una prueba automática con Chrome sin ventana que verificó la lógica y el caso "ya activo al cargar", en lugar de una lista de pruebas manuales.
3. Una instrucción de trabajo dentro del prompt largo: "Cuando yo te escriba 'documenta': escribe `docs/feedback/handover.md` con la plantilla (alternativas reales descartadas, referencias solo si estás seguro de que existen, limitaciones honestas) y anota en `../notas_ia.md` cada error tuyo o corrección mía". Salió una nota de diseño con alternativas reales y sin referencias inventadas (solo citó SAE J3016), y un registro de los errores del modelo.

**Uno que me engañó** (qué pediste, qué te dio, por qué estaba mal, cómo lo detectaste):

Pedí la feature terminada y probada. El modelo la entregó y me explicó cómo probarla sin haberla abierto en un navegador (avisó que no estaba verificada). Al ejecutar `autodrive(true)` no se veía ningún borde ni pastilla, y el modelo supuso que la causa era la caché del navegador sin comprobarlo. Lo detecté con mi captura de la consola; recargué sin caché y funcionó. Los demás incidentes del modelo están en `notas_ia.md`.

**Porcentaje aproximado del texto final del system prompt que escribió la IA sin cambios:** 80 %.

La IA redactó gran parte de las instrucciones, pero yo revisé las propuestas, identifiqué qué cambios funcionaban, decidí cuáles conservar. Las pruebas en el navegador las hice yo con la consola y mis capturas; la prueba automática con un navegador controlado por script y el push de la rama los hizo el modelo, con mi autorización.

Opcional: exporta las conversaciones a `logs/`.

# Reflexión (300 a 500 palabras)

**Equipo:** sofia_morato  
**Integrantes:** Sofía Morato  
**Features entregadas (ids):** `handover`  
**Enlace al pull request:** https://github.com/ignacioalvmar/prompt-drive/pull/28

## Qué quería lograr

La acción que más "muda" me pareció fue el traspaso de control. Cuando la persona dice "maneja tú", el asistente responde "listo, tomo el control" y el carro empieza a moverse solo, pero nada en la cabina muestra quién conduce. Al devolver el control tampoco hay ningún aviso. Me pareció la más importante porque quien maneja debe saber siempre quién está a cargo.

## Qué diseñé y qué pasó

Decidí un estado permanente y discreto: un borde fino violeta alrededor de la pantalla y una pastilla pequeña con un timón y la palabra AUTO, abajo al centro. Elegí el violeta porque el asistente ya usa cian, ámbar, blanco, verde y rojo, y quería que el color significara una sola cosa. Al activarse, el borde entra en 2,5 segundos con dos tonos ascendentes; al desactivarse, se desvanece en 1,5 segundos con un tono descendente y la pastilla dice MANUAL durante 2 segundos. Si el modo ya estaba activo al cargar, aparece sin animación ni sonido.

Descarté un texto grande, una cuenta regresiva y colores cálidos. La cuenta regresiva era imposible porque la feature solo ve el cambio cuando ocurre. Después de verlo funcionando, no hice cambios grandes porque el resultado se acercaba a lo que quería. Me enfoqué en comprobar que las transiciones fueran claras y que el indicador no estorbara ni llamara demasiado la atención.

## Dónde la IA me ayudó y dónde me engañó

Me ayudó a escribir la feature, a probar con un navegador controlado por script la lógica (etiquetas, número de tonos, estado inicial sin animación) y a preparar el guion del video. Me engañó al entregar la feature sin haberla abierto en un navegador: cuando no se veía nada, supuso que la causa era la caché sin comprobarlo. Lo detecté con mi captura de la consola, recargué sin caché y funcionó. Después le pedí que anotara cada error suyo en un registro.

## Qué haría con un segundo día

Mediría los tiempos de las transiciones en un navegador con ventana y probaría con personas si el violeta se entiende como "automático" sin explicación. También intentaría un aviso previo a la devolución del control, lo que requeriría que el motor publique la intención antes del cambio.

## Qué aprendí sobre la retroalimentación en el carro, o sobre cómo trabajo yo

Aprendí que un estado permanente y discreto comunica más que un aviso grande y breve, y que una limitación honesta (la feature solo refleja el cambio) es parte del diseño. La próxima vez que trabaje con IA, comprobaría desde el principio las instrucciones y los resultados que me da, en lugar de asumir que todo está bien. Entendí que la IA me puede ayudar a avanzar más rápido, pero que debo probar las cosas por mi cuenta y no confiar solamente en lo que me dice.
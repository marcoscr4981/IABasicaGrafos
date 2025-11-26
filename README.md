# IA Básica Grafos

Con este ejercicio he modificado una ruta para ir a un punto y creado una nueva zona con un botón para que el tanque vaya a esa ubicación.

> Con este ejercicio he tenido bastantes problemas. Cuando ejecutaba el programa se colgaba Unity y me fue complicado intentar hacer pruebas.

## Nuevo camino

Modifiqué la posición de los nodos para la acción del primer botón del Canvas (`GotoRuin`).


## Nuevo punto

He creado un nuevo punto `WP009` y un nuevo botón `Ejercicio Button`.

El nuevo punto lo he añadido en el Game Object WPManager:

- **Waypoints:** Es el elemento número 8.
- **Links:**
  - **Node 1:** WP009
  - **Node 2:** WP006
  - **Dir:** BI

En el script `TanksWaypointsFollow` he añadido el método:

```csharp
public void GotoEjercicio()
{
    graph.AStar(currentNode, waypoints[8]);
    currentWP = 0;
}
```

Cuando se ejecuta el juego y se hace clic en el botón `Ejercicio Button`, hace el siguiene trayecto: 

WP001 > WP002 > WP007 > WP006 > WP009

En cambio si como `Node 2` añado el punto `WP003`, hace el siguiente recorrido:

WP001 > WP002 > WP007 > WP003 > WP009
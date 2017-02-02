# <a name="using-the-preview3-folder-and-sub-folders"></a>Uso de la carpeta y las subcarpetas de preview3

Esta carpeta es el nodo de nivel superior que coincide con la carpeta de herramientas, pero contiene deltas de la versión .NET Core Tooling Preview 4.

El objetivo de esta estructura de carpetas paralela independiente es proporcionar una ubicación para el contenido relacionado con la versión Preview 4 que se pueda combinar con relativa facilidad en la estructura principal al proporcionar cambio de versión en el sitio publicado.

El contenido de este nodo debe ser un conjunto de documentos más pequeño que represente los deltas de la versión de compatibilidad a largo plazo (LTS) y la última versión actual. 

## <a name="structure"></a>Estructura

Hay dos casos para agregar nuevo contenido en esta versión:

* Cambios en los documentos existentes
    - Copie el contenido existente en una carpeta paralela en esta estructura. Realice los cambios y agregue el archivo modificado a la tabla de contenido de la versión Preview 4.
* Nuevos documentos
    - Coloque el nuevo documento en la ubicación apropiada y agréguelo a la tabla de contenido bajo el nodo de la versión Preview 4. 

Todos los archivos de versión actual deben tener agregado lo siguiente en la parte superior del tema:

[!include[current release track](../includes/warning.md)]

Hemos creado un fragmento de código para incluir con la siguiente sintaxis:

```markdown
[!include[current release track](../../includes/warning.md)]
```

### <a name="link-instructions"></a>Instrucciones de vínculo

En ambos casos, proporcionan vínculos de la versión actual a la página LTS (o index.md primario) con fines de navegación.
Considere la posibilidad de proporcionar vínculos de la página LTS (o index.md principal) a la nueva página de contenido de versión actual.

## <a name="future-considerations"></a>Consideraciones futuras

Nuestro objetivo final es sacar diferentes versiones como ramas en el [repositorio de documentos](https://github.com/dotnet/docs). Hasta que no se admita el escenario de publicación, usaremos distintas carpetas de nivel superior para cada versión actual. 

Cuando llegue el momento, podemos combinar cada versión actual en la carpeta de [documentos](../docs) principal, combinar los nodos de tabla de contenido y publicarla como un conjunto de documentos independiente. Puede que sea necesario combinar las modificaciones en ambas versiones LTS de un archivo y la versión actual de ese archivo, pero podremos encontrar esos cambios con relativa facilidad.


<!--HONumber=Jan17_HO3-->



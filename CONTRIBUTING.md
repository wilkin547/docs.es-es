---
ms.openlocfilehash: e5da9a98e8725880223df3737dc60f773db8d20e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79141138"
---
# <a name="contributing"></a>Contribución

Le agradecemos el interés en colaborar con la documentación de .NET.

> Estamos en proceso de trasladar nuestras instrucciones a una guía de contribuciones de todo el sitio.
> Para ver las nuevas instrucciones, visite la [introducción a la guía de colaboradores de Microsoft Docs](https://docs.microsoft.com/contribute/).

En este documento se describe el proceso para colaborar en los artículos y ejemplos de código que se hospedan en el [sitio de documentación de .NET](https://docs.microsoft.com/dotnet). Las contribuciones pueden ser tan simples como corregir errores ortográficos o tan complejos como redactar nuevos artículos.

- [Qué se debe hacer y qué no](#dos-and-donts)
- [Proceso de contribución](#process-for-contributing)
- [La experiencia interactiva de C#](#the-c-interactive-experience)
- [Contrato de licencia del colaborador](#contributor-license-agreement)

Este repositorio contiene documentación conceptual de .NET. El sitio de documentación de .NET se compiló a partir de varios repositorios, además de este:

- [Ejemplos de código y fragmentos de código](https://github.com/dotnet/samples) Se realiza un seguimiento de los problemas y tareas de este repositorio en [dotnet/docs/issues](https://github.com/dotnet/docs/issues).
- [Referencia de API .NET](https://github.com/dotnet/dotnet-api-docs) Se realiza un seguimiento de los problemas y tareas de este repositorio en [dotnet/dotnet-api-docs/issues](https://github.com/dotnet/dotnet-api-docs/issues).
- [Referencia del SDK de .NET Compiler Platform](https://github.com/dotnet/roslyn-api-docs) Se realiza un seguimiento de los problemas y tareas de este repositorio en [dotnet/docs/issues](https://github.com/dotnet/docs/issues).

### <a name="contributing-to-international-content"></a>Contribución a contenido internacional

Actualmente no se admiten las contribuciones de contenido de traducción automática (MT). En un esfuerzo por mejorar la calidad del contenido de MT, hemos realizado la transición a un motor neuronal de MT. Aceptamos y fomentamos las contribuciones de contenido de traducción humana (HT), que se usa para entrenar el motor neuronal de MT. Por lo tanto, con el tiempo, las contribuciones al contenido de HT mejorarán la calidad de HT y MT. Los temas de MT tendrán una declinación de responsabilidades que indica que es posible que parte del tema sea MT y que el botón **Editar** no se mostrará cuando esté deshabilitado.

## <a name="dos-and-donts"></a>Qué hacer y qué no hacer

En la lista siguiente se muestran algunas reglas orientativas que se deben tener en cuenta a la hora de contribuir a la documentación de .NET:

- **NO** nos sorprenda con solicitudes de incorporación de cambios de gran tamaño. En su lugar, registre un asunto e inicie una discusión para que podamos definir un rumbo antes de dedicar una gran cantidad de tiempo. En el caso de los cambios en masa, divida el trabajo en solicitudes de incorporación de cambios más pequeñas (de hasta 100 archivos). Se recomienda encarecidamente esta instrucción si la solicitud de incorporación de cambios no sigue las instrucciones siguientes.
- **EXAMINE** las incidencias [up for grabs](https://github.com/dotnet/docs/labels/up-for-grabs) (para seleccionar) actuales para obtener sugerencias sobre tareas.
- **CREE** una solicitud de incorporación de cambios (PR) para cada tarea. Las PR que incluyen varios cambios no relacionados son mucho más difíciles de revisar. Esto retrasa las revisiones y la combinación de las PR. Esta instrucción también se aplica a las revisiones: evitamos sugerir cambios no relacionados en las revisiones; pedimos que las revisiones de la comunidad cumplan esta instrucción.
- **PROPORCIONE** una descripción clara del error en la PR. Díganos qué ha cambiado y por qué. La descripción predeterminada de "actualizar artículo.md" no es útil para los revisores.
- **NO** envíe PR para cambios que solo sean de estilo sin consultarlo antes. Estas PR requieren un tiempo adicional para revisar la precisión y su combinación suele provocar conflictos de combinación con otras actualizaciones importantes. Estamos trabajando para seguir un estilo coherente, pero equilibramos ese trabajo con otras tareas. Los artículos se adecúan para que cumplan el estilo cuando se realizan actualizaciones importantes por otras razones.
- **LEA** la [guía de estilo](./styleguide/template.md) y las instrucciones de [voz y tono](./styleguide/voice-tone.md). Las nuevas adiciones deben seguir estas instrucciones.
- **CREE** una rama independiente en la bifurcación antes de trabajar en los artículos.
- **SIGA** el [flujo de trabajo de GitHub](https://guides.github.com/introduction/flow/).
- **HABLE** de sus contribuciones con frecuencia en blogs o Twitter (o cualquier otra red social).

Estas instrucciones nos ayudan a respetar el tiempo de todo el mundo. Muchos usuarios contribuyen a estos repositorios. Si sigue estas instrucciones, nos resultará más fácil revisar y combinar la PR a tiempo. Estos procedimientos minimizan los conflictos con las PR de otros miembros de la comunidad y nuestro equipo. Como las solicitudes de incorporación de cambios que no siguen estas instrucciones suelen provocar trabajo adicional para nosotros y los miembros de la comunidad, es posible que se rechacen. Si quiere una excepción, empiece por crear una incidencia.

> Nota: Tal vez observe que algunos de los temas no siguen actualmente todas las instrucciones que se especifican aquí y en la [guía de estilo](./styleguide/template.md). pero estamos trabajando para dar coherencia a todo el sitio.

## <a name="process-for-contributing"></a>Proceso de contribución

Necesita tener conocimientos básicos de [Git y GitHub.com](https://guides.github.com/activities/hello-world/).

**Paso 1:** En el caso de pequeños cambios, omita este paso (por ejemplo, si corrige un error de escritura o abre inmediatamente una solicitud de incorporación de cambios para resolver un problema que encuentre en los documentos). Si está interesado en escribir nuevo contenido o en revisar exhaustivamente el contenido existente, abra una [incidencia ](https://github.com/dotnet/docs/issues) que describa lo que quiere hacer.
El contenido de la carpeta *docs* se organiza en secciones que se reflejan en la tabla de contenido (TOC). Defina dónde se ubicará el tema en la tabla de contenido. Recabe opiniones sobre su propuesta.

o bien

Puede elegir entre las incidencias existentes aquellas en las que las contribuciones son bienvenidas. En [Projects for .NET Community contributors](https://github.com/dotnet/docs/projects/35) (Proyectos para los colaboradores de la comunidad de .NET) se muestran muchos de los elementos de trabajo que están disponibles para los colaboradores de la comunidad. En función de sus intereses y su nivel de compromiso, puede elegir entre las incidencias de las siguientes categorías:

- **Mantenimiento**. Esta categoría incluye contribuciones bastante sencillas, como la corrección de vínculos rotos o incorrectos, la adición de ejemplos de código que faltan o la solución de incidencias de contenido limitado. En algunos casos, es posible que estas incidencias afecten a gran cantidad de archivos. En ese caso, debe comunicarnos en qué le gustaría trabajar antes de comenzar.

- **Actualizaciones de contenido**. Dada la enormidad del conjunto de documentos, el contenido se vuelve fácilmente obsoleto y requiere revisión. Además, por diversos motivos, parte del contenido se ha duplicado o incluso triplicado. La actualización de contenido implica asegurarse de que los temas individuales están actualizados o revisar el contenido de un área de características para eliminar la duplicación y garantizar que todo el contenido único se conserve en el conjunto de documentación más pequeño.

- **Creación de nuevo contenido**. Si está interesado en crear su propio tema, estas incidencias muestran los temas que sabemos que nos gustaría agregar a nuestro conjunto de documentación. Pero, antes de empezar a trabajar en un tema, comuníquenoslo. Si está interesado en escribir un tema que no aparece aquí, abra una incidencia.

También puede consultar nuestra lista de [incidencias abiertas](https://github.com/dotnet/docs/issues) y ofrecerse para trabajar en las que le interesan. Se utiliza la etiqueta [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) para identificar las incidencias abiertas para la contribución.

**Paso 2:** Bifurque los repositorios `dotnet/docs`, `dotnet/samples` o `dotnet/dotnet-api-docs` según sea necesario y cree una rama para los cambios.

Para realizar pequeños cambios, puede usar la interfaz web de GitHub. Simplemente haga clic en el botón **Edit the file in your fork of this project** (Editar el archivo en la bifurcación de este proyecto) en el archivo que quiere cambiar. GitHub creará automáticamente la nueva rama cuando se envíen los cambios.

**Paso 3:** Realice los cambios en esta nueva rama.

Si es un tema nuevo, puede usar esta [plantilla](./styleguide/template.md) como punto de partida. La plantilla contiene las instrucciones de escritura y la explicación de los metadatos necesarios para cada artículo, como la información del autor.

Vaya a la carpeta correspondiente a la ubicación de la tabla de contenido que se determinó para su artículo en el paso 1.
Esa carpeta contiene los archivos Markdown de todos los artículos incluidos en esa sección.
Si es necesario, cree una carpeta para colocar los archivos de su contenido. El artículo principal de esa sección se denomina *index.md*.
Para las imágenes y otros recursos estáticos, cree una subcarpeta denominada *media* dentro de la carpeta que contiene el artículo, si aún no existe. Dentro de la *media* carpeta, cree una subcarpeta con el nombre de artículo (excepto para el archivo de índice).
Incluya los ejemplos de mayor tamaño en la carpeta *samples* en la raíz del repositorio.

Asegúrese de seguir la sintaxis de Markdown adecuada. Para más información, vea la [guía de estilo](./styleguide/template.md).

### <a name="example-structure"></a>Estructura de ejemplo

```
docs
  /about
  /core
    /porting
      porting-overview.md
      /media
        /porting-overview
            portability_report.png
```

**Paso 4:** Envíe una solicitud de incorporación de cambios (PR) desde su rama a `dotnet/docs/master`, `dotnet/dotnet-api-docs/master` o `dotnet/samples/master`.

La PR *siempre* se debe destinar a la rama predeterminada del repositorio (a menos que trabaje en una rama de versión). En el caso de dotnet/docs, la rama principal es la rama predeterminada. Para los repositorios localizados, la rama activa es la predeterminada. *Nunca* debe abrir una PR que tenga como destino la rama activa en dotnet/docs.

Normalmente, cada PR debe abordar las incidencias una a una. La PR puede modificar uno o varios archivos. Si se abordan varias correcciones en distintos archivos, es preferible usar PR independientes.

Si la PR aborda una incidencia existente, agregue la palabra clave `Fixes #Issue_Number` al mensaje de confirmación o a la descripción de la PR. De este modo, la incidencia se podrá cerrar automáticamente cuando se combine la PR. Para obtener más información, vea [Closing issues via commit messages](https://help.github.com/articles/closing-issues-via-commit-messages/) (Cierre de asuntos mediante mensajes de confirmación).

El equipo de .NET revisará la PR y comunicará si es necesario realizar otras actualizaciones o modificaciones para aprobarla.

**Paso 5:** Realice las actualizaciones necesarias a la rama que haya acordado con el equipo.

Los encargados del mantenimiento combinarán la PR con la rama maestra una vez que se hayan aplicado los comentarios y se apruebe el cambio.

Las confirmaciones de la rama principal se insertan en la rama en vivo siguiendo un ritmo determinado. Una vez insertadas, podrá ver su contribución en https://docs.microsoft.com/dotnet/.

### <a name="contributing-to-samples"></a>Contribución a los ejemplos

Hacemos la siguiente distinción para el código que existe en nuestro repositorio:

- Ejemplos: los lectores pueden descargar y ejecutar los ejemplos. Todos los ejemplos deben ser aplicaciones o bibliotecas completas. Si el ejemplo crea una biblioteca, debe incluir pruebas unitarias o una aplicación que permita a los lectores ejecutar el código.

- Fragmentos de código: ilustran un concepto o una tarea de menor tamaño. Se compilan, pero no pretenden ser aplicaciones completas.

Todo el código reside en el repositorio [dotnet/samples](https://github.com/dotnet/samples). Trabajamos hacia un modelo en el que la estructura de nuestra carpeta samples coincide con la estructura de nuestra carpeta docs. Los estándares que seguimos son:

- La carpeta *snippets* de nivel superior contiene fragmentos de código para ejemplos pequeños y centrados.
- Los ejemplos de referencia de API han estado en una carpeta que sigue este patrón: *snippets/\<idioma>/api/\<espacio de nombres>/\<nombre de la api>* .
- Otras carpetas de nivel superior coinciden con las carpetas de nivel superior del repositorio *docs*. Por ejemplo, el repositorio de documentos incluye una carpeta *machine-learning/tutorials* y los ejemplos para tutoriales de aprendizaje automático se encuentran en la carpeta *samples/machine-learning/tutorials*.

Además, todos los ejemplos de las carpetas *core* y *standard* se deben compilar y ejecutar en todas las plataformas compatibles con .NET Core. Nuestro sistema de compilación de CI aplicará esto. La carpeta *framework* de nivel superior contiene ejemplos que solo se compilan y validan en Windows.

Podemos ampliar estos directorios a medida que el repositorio de documentos agrega contenido nuevo. Por ejemplo, agregaremos directorios de Xamarin, como los directorios `xamarin-ios` y `xamarin-android`.

Cada ejemplo completo que cree debe contener un archivo *readme.md*. Este archivo debe contener una descripción breve del ejemplo (uno o dos párrafos). Su archivo *readme.md* debe indicar a los lectores lo que aprenden a través de este ejemplo. El archivo *readme.md* debe contener también un vínculo al documento activo en el [sitio de documentación de .NET](https://docs.microsoft.com/dotnet/welcome).
Para saber dónde un determinado archivo del repositorio se asigna a ese sitio, reemplace `/docs` en la ruta de acceso de repositorio por `https://docs.microsoft.com/dotnet`.

El tema contendrá también vínculos al ejemplo. Se vincula directamente a la carpeta del ejemplo en GitHub.

Para más información, vea el archivo [Léame de samples](https://github.com/dotnet/samples/blob/master/README.md).

## <a name="the-c-interactive-experience"></a>La experiencia interactiva de C#

Los ejemplos de código corto en C# pueden usar la etiqueta de idioma `csharp-interactive` para especificar un ejemplo de C# que se ejecuta en el navegador. (Los ejemplos de código en línea usan la etiqueta `csharp-interactive`, para fragmentos de código incluidos en el origen, usan la etiqueta `code-csharp-interactive`). Estos ejemplos de código muestran una ventana de código y una ventana de salida en el artículo. La ventana de salida muestra el resultado de ejecutar el código interactivo cuando el usuario haya ejecutado el ejemplo.

La experiencia interactiva de C# cambia la forma en que se trabaja con ejemplos. Los visitantes pueden ejecutar el ejemplo para ver la salida. Una serie de factores ayudan a determinar si el ejemplo o el texto correspondiente deben incluir información sobre la salida.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Cuándo se debe mostrar la salida esperada sin ejecutar el ejemplo

- Los artículos dirigidos a principiantes deben ofrecer una salida para que los lectores pueden comparar la salida de su trabajo con la respuesta esperada.
- Los ejemplos en los que la salida es parte integral del tema deben mostrar esa salida. Por ejemplo, los artículos en texto con formato deben mostrar el formato de texto sin ejecutar el ejemplo.
- Cuando tanto el ejemplo como la salida esperada es breve, considere la posibilidad de mostrar la salida. Ahorra un poco de tiempo.
- Los artículos que describen cómo la referencia cultural actual o la referencia cultural invariable inciden en la salida deben explicar la salida esperada. El REPL (read–eval–print loop) interactivo se ejecuta en un host basado en Linux. La referencia cultural predeterminada y la referencia cultural invariable generan distintas salidas en los distintos sistemas operativos y máquinas. En el artículo se debe explicar la salida en los sistemas Windows, Linux y Mac.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Cuándo debe excluirse la salida esperada del ejemplo

- Los artículos en los que el ejemplo genera una salida de mayor tamaño no deben incluirla en los comentarios. Oculta el código una vez que se ha ejecutado el ejemplo.
- Los artículos en los que el ejemplo muestra un tema, pero la salida no es suficiente para su comprensión. Por ejemplo, código que ejecuta una consulta LINQ para explicar la sintaxis de consulta y luego muestra todos los elementos en la colección de salida.

## <a name="contributor-license-agreement"></a>Contrato de licencia del colaborador

Debe firmar el [contrato de licencia de colaboración (CLA) de .NET Foundation](https://cla.dotnetfoundation.org) antes de que la PR se combine. Se trata de un requisito único para los proyectos de .NET Foundation. Puede obtener más información sobre los [contratos de licencia de colaboración (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement) en Wikipedia.

El contrato: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

No tiene que firmar el contrato con antelación. Puede clonar, bifurcar y enviar la PR de la forma habitual. Cuando se haya creado la PR, un bot de CLA se encargará de clasificarla. Si el cambio no es relevante (por ejemplo, si se ha corregido un error ortográfico), la PR se etiqueta como `cla-not-required`. En caso contrario, se clasifica como `cla-required`. Cuando haya firmado el CLA, las solicitudes de incorporación de cambios actual y futuras se etiquetarán como `cla-signed`.

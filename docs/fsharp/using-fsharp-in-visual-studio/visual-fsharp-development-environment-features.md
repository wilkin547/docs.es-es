---
title: Características del entorno de desarrollo de F#
description: 'Obtenga información acerca de qué características de Visual Studio 2012 se admiten en F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: dd5c3165a73bd4f821a26d183094829dab7eaeae
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="visual-f-development-environment-features"></a>Características del entorno de desarrollo de Visual F#

> [!NOTE]
En este artículo no está actualizado con el más reciente de Visual Studio.  Se va a actualizar.

Este tema incluye información acerca de qué características de Visual Studio 2012 se admiten en F #.

## <a name="project-features"></a>Características de proyecto
En la tabla siguiente se resume las plantillas que están disponibles para su uso en proyectos de F #. Para obtener información acerca de las plantillas de proyecto y elemento, vea [NIB crear proyectos a partir de plantillas](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2).

|Tipo de plantilla|Descripción|Plantillas compatibles|
|-------------|-----------|-------------------|
|Plantillas de proyecto|Tipos de proyectos disponibles en la **nuevo proyecto** cuadro de diálogo.|<ul><li>Aplicación de F #<br /></li><li>Biblioteca de F #<br /></li><li>Tutorial de F #<br /></li><li>Biblioteca Portable de F #<br /></li><ul/>|
|Plantillas de elementos|Tipos de archivos disponibles en la **Agregar nuevo elemento** cuadro de diálogo.|<ul><li>Archivo de código fuente de F # (.fs)<br /></li><li>Script de F # (.fsx)<br /></li><li>Archivo de signatura de F # (.fsi)<br /></li><li>Archivo de configuración (.config)<br /></li><li>Conexión de base de datos de SQL (proveedor de tipos de LINQ to SQL)<br /></li><li>Conexión de base de datos de SQL (proveedor LINQ to Entities tipo)<br /></li><li>Conexión de servicio de OData (proveedor de tipos LINQ)<br /></li><li>Conexión de servicio de WSDL (proveedor de tipo)<br /></li><li>Archivo XML (.xml)<br /></li><li>Archivo de texto<br /></li><ul/>|
Para crear una aplicación que se puede ejecutar un archivo ejecutable independiente, elija el tipo de proyecto de aplicación de F #. Para crear una biblioteca (es decir, un ensamblado administrado o. Archivo DLL) para su uso en la plataforma de escritorio de Windows, elija la biblioteca de F #. Para crear una biblioteca portable que se puede usar en cualquier plataforma compatible, elija Biblioteca Portable de F #. Proyectos de biblioteca Portable de F # hacen referencia a una versión de FSharp.Core.dll que es adecuado para crear una biblioteca de F # que puede usarse con aplicaciones que se ejecutan en plataformas como aplicaciones de la tienda de Windows, el .NET Framework 4.5, Xamarin.iOS y Xamarin.Android.

Para obtener más información acerca de las plantillas de elementos para el acceso a datos, vea [proveedores de tipo](../tutorials/type-providers/index.md).

En la tabla siguiente se resume las características de propiedades del proyecto compatibles y no compatibles en F #. Para obtener más información, consulte [configurar proyectos](configuring-projects.md) y [Introducción al diseñador de proyectos](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7).

|Configuración del proyecto|¿Se admite en F #?|Notas|
|---------------|----------------|-----|
|Archivos de recursos|Sí||
|Compilación, depuración y la configuración de referencia|Sí||
|Compatibilidad con múltiples versiones (multi-targeting)|Sí||
|Icono y manifiesto|No|Disponible a través de opciones del compilador de línea de comandos.|
|Servicios de cliente ASP.NET|No||
|ClickOnce|No|Utilizar un proyecto de cliente en otro lenguaje de .NET Framework, si procede.|
|Nombre seguro|No|Disponible a través de opciones del compilador de línea de comandos.|
|Ensamblado de publicación y control de versiones|No||
|Análisis de código|No|Herramientas de análisis de código se pueden ejecutar manualmente o como parte de un comando posterior a la compilación.|
|Seguridad (cambiar niveles de confianza)|No||

## <a name="code-and-text-editor-features"></a>Características de Editor de texto y código
Se admiten las siguientes características de los editores de texto y Studiocode Visual en F #. Para obtener información general sobre la edición de código en Visual Studio y las características del editor de texto, consulte [escribir código en el Editor de texto y código](/visualstudio/ide/writing-code-in-the-code-and-text-editor).

|Característica|Descripción|¿Se admite en F #?|
|-------|-----------|----------------|
|Marcar automáticamente como comentario|Puede acotar como comentario o secciones de código.|Sí|
|Dar formato automáticamente|Cambia el formato de código con sangría estándar y el estilo.|No|
|Marcadores|Permite guardar lugares en el editor.|Sí|
|Cambiar la sangría|Aplica una sangría o anula la sangría de las líneas seleccionadas.|Sí|
|[Buscar y reemplazar texto](/visualstudio/ide/finding-and-replacing-text)|Permite buscar en un archivo, proyecto o solución y, potencialmente, cambiar texto.|Sí|
|Vaya a la definición de la API de .NET Framework|Cuando el cursor se sitúa en una API de .NET Framework, muestra código generado a partir de metadatos de .NET Framework.|No|
|Vaya a la definición de la API definida por el usuario|Cuando el cursor está en una entidad de programa que ha definido, mueve el cursor a la ubicación en el código donde se define la entidad.|Sí|
|Ir a la línea|Le permite obtener acceso a una línea específica en un archivo, por número de línea.|Sí|
|Barras de navegación en la parte superior del archivo|Le permite saltar a ubicaciones del código, por ejemplo, nombre de la función.|Sí|
|Esquematización. Vea [esquematización](/visualstudio/ide/outlining).|Puede contraer secciones del código para crear una vista más compacta.|Sí|
|Aplicar tabulaciones a|Convierte los espacios en tabulaciones.|Sí|
|Uso de colores para el tipo|Muestra los nombres de tipo definidos en un color especial.|Sí|
|Búsqueda rápida. Vea búsqueda rápida, buscar y reemplazar (ventana).|Permite buscar en un archivo o proyecto.|Sí|

## <a name="intellisense-features"></a>Características de IntelliSense
En la tabla siguiente se resume las características de IntelliSense compatibles y no compatibles en F #. Para obtener información general acerca de IntelliSense, vea [utilizar IntelliSense](/visualstudio/ide/using-intellisense).

|Característica|Descripción|¿Se admite en F #?|
|-------|-----------|----------------|
|Implementar interfaces automáticamente|Genera código auxiliar para los métodos de interfaz.|No|
|Fragmentos de código|Inserta código desde una biblioteca de construcciones de codificación comunes en temas.|No|
|Palabra completa|Evita tener que escribir completando palabras y nombres a medida que escribe.|Sí|
|Modo de finalización de uso sin selección|Cuando está habilitado, hace la finalización automática de palabras seleccionar la primera coincidencia mientras se escribe, en lugar de esperar para que seleccione una o presione **CTRL+BARRA espaciadora**.|No|
|Generar elementos de código|Permite generar código auxiliar para una serie de construcciones de.|No|
|Lista de miembros|Cuando se escribe el operador de acceso de miembro (.), muestra a los miembros de un tipo.|Sí|
|Organizar instrucciones using/Open|Organiza los espacios de nombres al que hace referencia **con** instrucciones en C# o **abrir** directivas en F #.|No|
|Información de parámetros|Muestra información útil acerca de los parámetros a medida que escribe una llamada de función.|Sí|
|Información rápida|Muestra la declaración completa de cualquier identificador en el código.|Sí|
No admite la refactorización de código de F # en Visual Studio 2012.

## <a name="debugging-features"></a>Características de depuración
En la tabla siguiente se resume las características que están disponibles cuando se depura código de F #. Para obtener información general sobre el depurador de Visual Studio, vea [depurar en Visual Studio](https://msdn.microsoft.com/library/sc65sadd.aspx).

|Característica|Descripción|¿Se admite en F #?|
|-------|-----------|----------------|
|Ventana Automático|Muestra variables automáticas o temporales.|No|
|Puntos de interrupción|Permite pausar la ejecución de código en puntos concretos durante la depuración.|Sí|
|Puntos de interrupción condicionales|Permite a los puntos de interrupción que una condición que determina si debe pausar la ejecución de pruebas.|Sí|
|Editar y continuar|Permite que el código se modifica y se compila cuando se depura un programa en ejecución sin detener y reiniciar al depurador.|No|
|Evaluador de expresiones|Evalúa y ejecuta código en tiempo de ejecución.|No, pero C# puede utilizarse evaluador de expresiones, aunque debe utilizar la sintaxis de C#.|
|Depuración histórica|Le permite ir al código ejecutada anteriormente.|Sí|
|Ventana Locales|Muestra localmente definidos valores y variables.|Sí|
|Ejecutar hasta el cursor|Permite ejecutar código hasta que se alcanza la línea que contiene el cursor.|Sí|
|Paso a paso por instrucciones|Permite avanzar la ejecución y mover a cualquier llamada a función.|Sí|
|Paso a paso por procedimientos|Permite avanzar la ejecución en el marco de pila actual y moverse más allá de cualquier llamada a función.|Sí|

## <a name="additional-tools"></a>Herramientas adicionales
En la tabla siguiente se resume la compatibilidad de F # en Visual Studio tools.

|Herramienta|Descripción|¿Se admite en F #?|
|----|-----------|----------------|
|Jerarquía de llamadas|Muestra la estructura anidada de función que se llama en el código.|No|
|Métricas de código|Recopila información acerca del código, como números de línea.|No|
|Vista de clases|Proporciona una vista basada en el tipo del código en un proyecto.|No|
|[Lista de errores (Ventana)](/visualstudio/ide/reference/error-list-window)|Muestra una lista de errores en el código.|Sí|
|[F# Interactive](../tutorials/fsharp-interactive/index.md)|Permite que escriba (o copie y pegue) F # de código y ejecutarlo inmediatamente, independientemente de la generación del proyecto. La ventana de F # Interactive es una lectura, Evaluate, Print Loop (REPL).|Sí|
|Examinador de objetos|Le permite ver los tipos en un ensamblado.|Tipos de F # tal y como aparecen en los ensamblados compilados no aparecen tal y como se crearlos. Puede examinar la representación compilada de tipos de F #, pero no podrá ver los tipos tal y como aparecen en F #.|
|[Resultados (Ventana)](/visualstudio/ide/reference/output-window)|Muestra los resultados de compilación.|Sí|
|Análisis de rendimiento|Proporciona herramientas para medir el rendimiento del código.|Sí|
|Ventana Propiedades|Muestra y permite la edición de propiedades del objeto en el entorno de desarrollo que tiene el foco.|Sí|
|[Explorador de servidores](https://msdn.microsoft.com/library/x603htbk.aspx)|Proporciona métodos para interactuar con una variedad de recursos del servidor.|Sí|
|Explorador de soluciones|Permite ver y administrar proyectos y archivos.|Sí|
|Lista de tareas|Permite administrar los elementos de trabajo que pertenecen a su código.|Sí|
|Proyectos de prueba|Proporciona características que le ayudarán a probar el código.|No|
|Cuadro de herramientas|Muestra pestañas que contienen objetos arrastrables como controles y secciones de texto o código.|Sí|

## <a name="see-also"></a>Vea también
 [Empezar a trabajar con F # en Visual Studio](../get-started/get-started-visual-studio.md)  
 [Configurar proyectos](configuring-projects.md)  

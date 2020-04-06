---
title: 'Descripción de AssemblyLoadContext: .Net Core'
description: Conceptos clave para comprender la finalidad y el comportamiento de AssemblyLoadContext en .NET Core.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 43fb0d792ddeb20b8a141af452a86dd50f37ba43
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523610"
---
# <a name="understanding-systemruntimeloaderassemblyloadcontext"></a>Descripción de System.Runtime.Loader.AssemblyLoadContext

La clase <xref:System.Runtime.Loader.AssemblyLoadContext> es única en .NET Core. En este artículo se intenta complementar la documentación de la API <xref:System.Runtime.Loader.AssemblyLoadContext> con información conceptual.

Este artículo es relevante para los desarrolladores que implementan carga dinámica, en particular los desarrolladores de marco de carga dinámica.

## <a name="what-is-the-assemblyloadcontext"></a>¿Qué es AssemblyLoadContext?

Cada aplicación de .NET Core usa implícitamente <xref:System.Runtime.Loader.AssemblyLoadContext>.
Es el proveedor del runtime para buscar y cargar las dependencias. Cada vez que se carga una dependencia, se invoca una instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> para buscarla.

- Proporciona un servicio de búsqueda, carga y almacenamiento en caché de ensamblados administrados y otras dependencias.

- Para admitir la carga y descarga de código dinámico, crea un contexto aislado con el fin de cargar el código y sus dependencias en su propia instancia de <xref:System.Runtime.Loader.AssemblyLoadContext>.

## <a name="when-do-you-need-multiple-assemblyloadcontext-instances"></a>¿Cuándo necesita varias instancias de AssemblyLoadContext?

Una única instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> se limita a cargar exactamente una versión de un elemento <xref:System.Reflection.Assembly> por nombre de ensamblado simple, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>.

Esta restricción puede convertirse en un problema cuando se cargan módulos de código de forma dinámica. Cada módulo se compila de forma independiente y puede depender de distintas versiones de un elemento <xref:System.Reflection.Assembly>. Este problema se produce normalmente cuando distintos módulos dependen de versiones diferentes de una biblioteca usada habitualmente.

Para admitir la carga de código de forma dinámica, la API <xref:System.Runtime.Loader.AssemblyLoadContext> proporciona versiones en conflicto de carga de un elemento <xref:System.Reflection.Assembly> en la misma aplicación. Cada instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> proporciona un diccionario único que asigna cada <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> a una instancia de <xref:System.Reflection.Assembly> concreta.

También proporciona un mecanismo práctico para agrupar las dependencias relacionadas con un módulo de código para su descarga posterior.

## <a name="what-is-special-about-the-assemblyloadcontextdefault-instance"></a>¿Qué tiene de especial la instancia de AssemblyLoadContext.Default?

La instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> la rellena automáticamente el runtime en el inicio.  Utiliza el [sondeo predeterminado](default-probing.md) para buscar y encontrar todas las dependencias estáticas.

Resuelve los escenarios de carga de dependencias más comunes.

## <a name="how-does-assemblyloadcontext-support-dynamic-dependencies"></a>¿Cómo admite AssemblyLoadContext las dependencias dinámicas?

<xref:System.Runtime.Loader.AssemblyLoadContext> tiene varios eventos y funciones virtuales que se pueden invalidar.

La instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> solo admite la invalidación de los eventos.

Los artículos [Algoritmo de carga de ensamblado administrado](loading-managed.md), [Algoritmo de carga de ensamblado satélite](loading-resources.md) y [Algoritmo de carga de biblioteca no administrada (nativa)](loading-unmanaged.md) hacen referencia a todos los eventos y funciones virtuales disponibles.  En los artículos se muestra la posición relativa de cada evento y función en los algoritmos de carga. En este artículo no se reproduce esa información.

En esta sección se tratan los principios generales de las funciones y eventos relevantes.

- **Ser reiterativo**. Una consulta para una dependencia concreta siempre debe tener como resultado la misma respuesta. Se debe devolver la misma instancia de dependencia cargada. Este requisito es fundamental para la coherencia de la caché. En el caso concreto de los ensamblados administrados, creamos una caché de <xref:System.Reflection.Assembly>. La clave de caché es un nombre de ensamblado sencillo, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>.
- **Normalmente no se inician**.  Se espera que estas funciones devuelvan `null`, en lugar de iniciarse, cuando no se pueda encontrar la dependencia solicitada. El inicio finalizará la búsqueda prematuramente y propagará una excepción al autor de la llamada. El inicio se debe restringir a errores inesperados, como un ensamblado dañado o una condición de memoria insuficiente.
- **Evitar la recursividad**. Tenga en cuenta que estas funciones y controladores implementan las reglas de carga para buscar dependencias. Su implementación no debe llamar a las API que desencadenan la recursividad. Normalmente, el código debería llamar a las funciones de carga **AssemblyLoadContext** que requieran una ruta de acceso concreta o un argumento de referencia de memoria.
- **Cargar en el elemento AssemblyLoadContext correcto**. La elección de dónde cargar las dependencias es específica de la aplicación.  Estos eventos y funciones implementan la opción. Cuando el código llama a las funciones de carga por ruta de acceso **AssemblyLoadContext**, les llama en la instancia en la que se quiere cargar el código. En algún momento, devolver `null` y permitir que <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> controle la carga puede ser la opción más sencilla.
- **Tenga en cuenta las carreras de subprocesos**. La carga la pueden desencadenar varios subprocesos. AssemblyLoadContext controla las carreras de subprocesos mediante la adición atómica de ensamblados a su caché. La instancia del que pierde la carrera se descarta. En la lógica de implementación, no agregue lógica adicional que no controle correctamente varios subprocesos.

## <a name="how-are-dynamic-dependencies-isolated"></a>¿Cómo se aíslan las dependencias dinámicas?

Cada instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> representa un ámbito único para instancias de <xref:System.Reflection.Assembly> y definiciones de <xref:System.Type>.

No existe aislamiento binario entre estas dependencias. Solo están aisladas por no encontrarse entre sí por nombre.

En cada <xref:System.Runtime.Loader.AssemblyLoadContext>:

- <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> puede hacer referencia a una instancia de <xref:System.Reflection.Assembly> distinta.
- <xref:System.Type.GetType%2A?displayProperty=nameWithType> puede devolver una instancia de tipo distinta para el mismo tipo `name`.

## <a name="how-are-dependencies-shared"></a>¿Cómo se comparten las dependencias?

Las dependencias se pueden compartir fácilmente entre instancias de <xref:System.Runtime.Loader.AssemblyLoadContext>. El modelo general es que un elemento <xref:System.Runtime.Loader.AssemblyLoadContext> cargue una dependencia.  El otro comparte la dependencia mediante el uso de una referencia en el ensamblado cargado.

Este uso compartido es necesario para los ensamblados en runtime. Estos ensamblados solo se pueden cargar en <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>. Lo mismo se requiere en el caso de marcos como `ASP.NET`, `WPF` o `WinForms`.

Se recomienda cargar las dependencias compartidas en <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>. Este uso compartido es el modelo de diseño común.

El uso compartido se implementa en la codificación de la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> personalizada. <xref:System.Runtime.Loader.AssemblyLoadContext> tiene varios eventos y funciones virtuales que se pueden invalidar. Cuando alguna de estas funciones devuelve una referencia a una instancia de <xref:System.Reflection.Assembly> que se ha cargado en otra instancia de <xref:System.Runtime.Loader.AssemblyLoadContext>, se comparte la instancia de <xref:System.Reflection.Assembly>. El algoritmo de carga estándar se aplaza a <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> para cargar con el fin de simplificar el patrón común de uso compartido.  Consulte [Algoritmo de carga de ensamblado administrado](loading-managed.md).

## <a name="complications"></a>Complicaciones

### <a name="type-conversion-issues"></a>Incidencias de conversión de tipos

Cuando dos instancias de <xref:System.Runtime.Loader.AssemblyLoadContext> contienen definiciones de tipo con el mismo `name`, no son del mismo tipo. Son del mismo tipo si y solo si proceden de la misma instancia de <xref:System.Reflection.Assembly>.

Para complicar las cosas, los mensajes de excepción sobre estos tipos no coincidentes pueden ser confusos. Se hace referencia a los tipos en los mensajes de excepción por sus nombres de tipo simple. En este caso, el mensaje de excepción común tendría el formato siguiente:

> El objeto de tipo "IsolatedType" no se puede convertir al tipo "IsolatedType".

### <a name="debugging-type-conversion-issues"></a>Depuración de incidencias de conversión de tipos

Dado un par de tipos no coincidentes, es importante conocer también lo siguiente:

- El elemento <xref:System.Type.Assembly?displayProperty=nameWithType> de cada tipo.
- El elemento <xref:System.Runtime.Loader.AssemblyLoadContext> de cada tipo., que se puede obtener a través de la función <xref:System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(System.Reflection.Assembly)?displayProperty=nameWithType>.

Dado dos objetos `a` y `b`, la evaluación en el depurador de lo siguiente resultará útil:

```csharp
// In debugger look at each assembly's instance, Location, and FullName
a.GetType().Assembly
b.GetType().Assembly
// In debugger look at each AssemblyLoadContext's instance and name
System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(a.GetType().Assembly)
System.Runtime.Loader.AssemblyLoadContext.GetLoadContext(b.GetType().Assembly)
```

### <a name="resolving-type-conversion-issues"></a>Resolución de incidencias de conversión de tipos

Existen dos modelos de diseño para resolver estas incidencias de conversión de tipos.

1. Usar tipos comunes compartidos. Este tipo compartido puede ser un tipo en runtime primitivo o puede implicar la creación de un nuevo tipo compartido en un ensamblado compartido.  A menudo, el tipo compartido es una [interfaz](../../csharp/language-reference/keywords/interface.md) definida en un ensamblado de aplicación. Vea también: [¿Cómo se comparten las dependencias?](#how-are-dependencies-shared).

2. Utilice técnicas de serialización para realizar la conversión de un tipo a otro.

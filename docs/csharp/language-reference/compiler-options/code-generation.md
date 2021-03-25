---
description: Opciones del compilador de C# para controlar la generación de código. Las opciones afectan al código generado por el compilador para una compilación determinada.
title: 'Opciones del compilador de C#: opciones de generación de código'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- DebugType compiler option [C#]
- Optimize compiler option [C#]
- Deterministic compiler option [C#]
- ProduceOnlyReferenceAssembly compiler option [C#]
ms.openlocfilehash: 6b66c50b408f9615bc3c63ab4dd46dbc4215c62f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482490"
---
# <a name="c-compiler-options-that-control-code-generation"></a>Opciones del compilador de C# para controlar la generación de código

Las opciones siguientes controlan la generación de código mediante el compilador. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **DebugType** / `-debug`: se emite (o no se emite) información de depuración.
- **Optimize** / `-optimize`: se habilitan las optimizaciones.
- **Deterministic** / `-deterministic`: se genera una salida equivalente byte a byte del mismo origen de entrada.
- **ProduceOnlyReferenceAssembly** / `-refonly`: se genera un ensamblado de referencia, en lugar de un ensamblado completo, como resultado principal.

## <a name="debugtype"></a>DebugType

La opción **DebugType** hace que el compilador genere información de depuración y la incluya en el archivo o los archivos de salida. La información de depuración se agrega de forma predeterminada para la configuración de compilación de *depuración*. Está desactivada de forma predeterminada para la configuración de compilación de *versión*.

```xml
<DebugType>pdbonly</DebugType>
```

En todas las versiones del compilador a partir de C# 6.0, no hay ninguna diferencia entre *pdbonly* y *full*. Elija *pdbonly*. Para cambiar la ubicación del archivo *.pdb*, vea [**PdbFile**](./advanced.md#pdbfile).

> [!IMPORTANT]
> Esta sección se aplica solo a los compiladores anteriores a C# 6.0.
> El valor de este elemento puede ser `full` o `pdbonly`. El argumento *full*, que es la opción predeterminada si no se especifica *pdbonly*, permite adjuntar un depurador al programa en ejecución. Al especificar *pdbonly* se permite depurar el código fuente cuando se inicia el programa en el depurador, pero solo se mostrará el ensamblador cuando el programa en ejecución se adjunta al depurador. Use esta opción para crear versiones de depuración. Si usa *Full*, tenga en cuenta que se producirá cierto impacto en la velocidad y el tamaño del código optimizado por JIT y un pequeño impacto en la calidad del código con *full*. Se recomienda *pdbonly* o ningún PDB para generar el código de la versión de lanzamiento. Una diferencia entre *pdbonly* y *full* es que con *full* el compilador emite una instancia de <xref:System.Diagnostics.DebuggableAttribute>, que se usa para indicar al compilador JIT que la información de depuración está disponible. Por tanto, aparecerá un error si el código contiene <xref:System.Diagnostics.DebuggableAttribute> establecido en false cuando se usa *full*. Para obtener más información sobre cómo configurar el rendimiento de depuración de una aplicación, vea [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

## <a name="optimize"></a>Optimización

La opción **Optimización** habilita o deshabilita las optimizaciones realizadas por el compilador para que el archivo de salida sea menor, más rápido y más eficaz. La opción *Optimización* está habilitada de forma predeterminada para una configuración de compilación de *versión*. Está desactivada de forma predeterminada para una configuración de compilación de *depuración*.

```xml
<Optimize>true</Optimize>
```

La opción **Optimización** se establece en la página de propiedades de **compilación** del proyecto en Visual Studio.

**Optimización** también indica a Common Language Runtime que optimice el código en tiempo de ejecución. De forma predeterminada, las optimizaciones están deshabilitadas. Especifique **Optimize+** para habilitar las optimizaciones. Al compilar un módulo para que lo use un ensamblado, use la misma configuración de **Optimización** que la del ensamblado. Se pueden combinar las opciones **Optimización** y [**Depuración**](#debugtype).

## <a name="deterministic"></a>Determinista

Hace que el compilador genere un ensamblado cuya salida byte a byte es idéntica en todas las compilaciones para las entradas idénticas.

```xml
<Deterministic></Deterministic>
```

De forma predeterminada, la salida del compilador de un conjunto dado de entradas es única, ya que el compilador agrega una marca de tiempo y un MVID que se genera a partir de números aleatorios. Use la opción `<Deterministic>` para generar un *ensamblado determinista*, cuyo contenido binario es idéntico en todas las compilaciones, siempre y cuando la entrada siga siendo la misma. En este tipo de compilación, los campos timestamp y MVID se reemplazarán por los valores derivados de un hash de todas las entradas de la compilación. El compilador tiene en cuenta las siguientes entradas que afectan al determinismo:

- La secuencia de parámetros de la línea de comandos.
- El contenido del archivo de respuesta .rsp del compilador.
- La versión exacta del compilador que se usa y los ensamblados a los que se hace referencia.
- La ruta de acceso del directorio actual.
- El contenido binario de todos los archivos pasados explícitamente al compilador, ya sea de manera directa o indirecta, incluidos los siguientes:
  - Archivos de código fuente
  - Ensamblados a los que se hace referencia
  - Módulos a los que se hace referencia
  - Recursos
  - Archivo de clave de nombre seguro
  - Archivos de respuesta @
  - Analizadores
  - Conjuntos de reglas
  - Otros archivos que pueden usar los analizadores
- La referencia cultural actual (para el idioma en el que se producen los diagnósticos y los mensajes de excepción).
- La codificación predeterminada (o página de códigos actual) si no se especifica la codificación.
- La existencia (o la inexistencia) de archivos y su contenido en las rutas de búsqueda del compilador (especificada, por ejemplo, mediante `-lib` o `-recurse`).
- La plataforma de Common Language Runtime (CLR) en la que se ejecuta el compilador.
- El valor de `%LIBPATH%`, que pueden afectar a la carga de dependencias del analizador.

Se puede usar la compilación determinista para establecer si un archivo binario se compila a partir de un origen de confianza. La salida determinista puede ser útil cuando el origen está disponible públicamente. También puede determinar si los pasos de compilación dependen de los cambios en los binarios que se usan en el proceso de compilación.

## <a name="produceonlyreferenceassembly"></a>ProduceOnlyReferenceAssembly

La opción **ProduceOnlyReferenceAssembly** indica que un ensamblado de referencia se debe mostrar en lugar de un ensamblado de implementación, como el resultado principal. El parámetro **ProduceOnlyReferenceAssembly** deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no se pueden ejecutar.

```xml
<ProduceOnlyReferenceAssembly></ProduceOnlyReferenceAssembly>
```

Los ensamblados de referencia son un tipo especial de ensamblado. Los ensamblados de referencia solo contienen la cantidad mínima de metadatos necesarios para representar la superficie de API públicas de la biblioteca. Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API. Para obtener más información, vea [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md).

Las opciones **ProduceOnlyReferenceAssembly** y [**ProduceReferenceAssembly**](output.md#producereferenceassembly) son mutuamente excluyentes.

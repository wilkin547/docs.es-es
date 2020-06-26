---
title: MDA de bindingFailure
description: Obtenga información sobre el Asistente para la depuración administrada (MDA) de bindingFailure, que se activa cuando un ensamblado no se carga en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- binding failure
- binding, failures
- MDAs (managed debugging assistants), binding failures
- assemblies [.NET Framework], binding failures
- managed debugging assistants (MDAs), binding failures
- BindingFailure MDA
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
ms.openlocfilehash: 98c7947c7e5d2a1f0af8c26744d3b292ed8cb4c4
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415633"
---
# <a name="bindingfailure-mda"></a>MDA de bindingFailure

El asistente para la depuración administrada (MDA) `bindingFailure` se activa cuando no se puede cargar un ensamblado.

## <a name="symptoms"></a>Síntomas

El código ha intentado cargar un ensamblado con una referencia estática o uno de los métodos del cargador, como <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>. No se ha cargado el ensamblado y se ha producido una excepción <xref:System.IO.FileNotFoundException> o <xref:System.IO.FileLoadException>.

## <a name="cause"></a>Causa

Si el tiempo de ejecución no puede cargar un ensamblado, se produce un error de enlace. Un error de enlace podría deberse a una de las siguientes situaciones:

- Common Language Runtime (CLR) no encuentra el ensamblado solicitado. Hay muchas razones por las que esto puede suceder, por ejemplo, que el ensamblado no esté instalado o que la aplicación no esté configurada correctamente para encontrar el ensamblado.

- Un problema habitual es cuando se pasa un tipo a otro dominio de aplicación, lo que exige que CLR cargue el ensamblado que contiene ese tipo en el otro dominio de aplicación. Es posible que el tiempo de ejecución no pueda cargar el ensamblado si el otro dominio de aplicación está configurado de forma diferente al dominio de aplicación original. Por ejemplo, los dos dominios de aplicación pueden tener diferentes valores de propiedad <xref:System.AppDomain.BaseDirectory%2A>.

- El ensamblado solicitado está dañado o no es un ensamblado.

- El código que intenta cargar el ensamblado no tiene los permisos de seguridad de acceso de código correctos para cargar ensamblados.

- Las credenciales de usuario no proporcionan los permisos necesarios para leer el archivo.

## <a name="resolution"></a>Solución

El primer paso es determinar por qué CLR no ha podido enlazar con el ensamblado solicitado. Hay muchas razones por las que el tiempo de ejecución puede no haber encontrado o cargado el ensamblado solicitado, como los escenarios de la sección Causa. Para eliminar la causa del error de enlace, se recomiendan las siguientes acciones:

- Determine la causa con los datos proporcionados por el MDA `bindingFailure`:

  - Ejecute [Fuslogvw.exe (Visor de registro de enlaces de ensamblados)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) para leer los registros de errores generados por el enlazador de ensamblados.

  - Determine si el ensamblado se encuentra en la ubicación solicitada. En el caso de los métodos <xref:System.Reflection.Assembly.LoadFrom%2A> y <xref:System.Reflection.Assembly.LoadFile%2A>, la ubicación solicitada se puede determinar fácilmente. En el caso del método <xref:System.Reflection.Assembly.Load%2A>, que enlaza con la identidad del ensamblado, debe buscar ensamblados que coincidan con esa identidad en la ruta de acceso de sondeo de la propiedad <xref:System.AppDomain.BaseDirectory%2A> del dominio de aplicación y la memoria caché global de ensamblados.

- Resuelva la causa en función de la determinación anterior. Las opciones de resolución posibles son las siguientes:

  - Instale el ensamblado solicitado en la caché global de ensamblados y llame al método <xref:System.Reflection.Assembly.Load%2A> para cargar el ensamblado por identidad.

  - Copie el ensamblado solicitado en el directorio de la aplicación y llame al método <xref:System.Reflection.Assembly.Load%2A> para cargar el ensamblado por identidad.

  - Vuelva a configurar el dominio de aplicación en el que se produjo el error de enlace para que incluya la ruta de acceso del ensamblado al cambiar la propiedad <xref:System.AppDomain.BaseDirectory%2A> o agregar rutas de acceso de sondeo privadas.

  - Cambie la lista de control de acceso del archivo para permitir que el usuario que ha iniciado sesión lea el archivo.

## <a name="effect-on-the-runtime"></a>Efecto en el Runtime

Este MDA no tiene ningún efecto en el CLR. Solo notifica datos sobre errores de enlace.

## <a name="output"></a>Output

El MDA notifica qué ensamblado no se ha podido cargar, incluida la ruta de acceso solicitada o el nombre para mostrar, el contexto de enlace, el dominio de aplicación en el que se ha solicitado la carga y el motivo del error.

El nombre para mostrar o la ruta de acceso solicitada pueden estar en blanco si estos datos no estaban a disposición de CLR. Si la llamada errónea era al método <xref:System.Reflection.Assembly.Load%2A>, es probable que el tiempo de ejecución no pudiera determinar el nombre para mostrar del ensamblado.

## <a name="configuration"></a>Configuración

```xml
<mdaConfig>
  <assistants>
    <bindingFailure />
  </assistants>
</mdaConfig>
```

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra una situación que puede activar este MDA:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Reflection;
namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            // This call attempts to load a nonexistent assembly.
            // The call will throw a System.IO.FileNotFound exception
            // and cause the activation of the bindingFailure MDA
            // if it is registered.
            Assembly.Load("NonExistentAssembly");
        }
    }
}
```

## <a name="see-also"></a>Consulte también

- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)

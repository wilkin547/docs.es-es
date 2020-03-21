---
title: MDA de loadFromContext
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: d0090a0272d1c3b6175b351175689df1e1e4fdbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181809"
---
# <a name="loadfromcontext-mda"></a>MDA de loadFromContext
El asistente para la depuración administrada (MDA) `loadFromContext` se activa si se carga un ensamblado en el contexto de `LoadFrom`. Esta situación puede producirse como resultado de llamar a <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> u otros métodos similares.  
  
## <a name="symptoms"></a>Síntomas  
 El uso de algunos métodos de cargador puede dar lugar a ensamblados que se carguen en el contexto de `LoadFrom`. El uso de este contexto puede provocar un comportamiento inesperado para la serialización, conversión y resolución de dependencias. Por lo general, se recomienda que los ensamblados se carguen en el contexto de `Load` para evitar estos problemas. Sin este MDA es difícil determinar en qué contexto se ha cargado un ensamblado.  
  
## <a name="cause"></a>Causa  
 Por lo general, un ensamblado se carga en el contexto de `LoadFrom` si se cargó desde una ruta de acceso fuera del contexto de `Load`, como la caché global de ensamblados o la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>.  
  
## <a name="resolution"></a>Solución  
 Configure las aplicaciones para que las llamadas a <xref:System.Reflection.Assembly.LoadFrom%2A> ya no sean necesarias. Puede usar las técnicas siguientes para hacerlo:  
  
- Instalar ensamblados en la caché global de ensamblados.  
  
- Coloque los ensamblados en el directorio <xref:System.AppDomainSetup.ApplicationBase%2A> del <xref:System.AppDomain>. En el caso del dominio predeterminado, el directorio <xref:System.AppDomainSetup.ApplicationBase%2A> es el que contiene el archivo ejecutable que inició el proceso. Es posible que esto también requiera crear un <xref:System.AppDomain> si no es conveniente mover el ensamblado.  
  
- Agregue una ruta de acceso de sondeo al archivo de configuración (.config) de la aplicación o a dominios de aplicación secundarios si los ensamblados dependientes se encuentran en directorios secundarios en relación con el archivo ejecutable.  
  
 En cada caso, se puede cambiar el código para usar el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 El MDA no tiene ningún efecto en el CLR. Informa del contexto que se usó como resultado de una solicitud de carga.  
  
## <a name="output"></a>Output  
 El MDA informa de que el ensamblado se cargó en el contexto de `LoadFrom`. Especifica el nombre simple del ensamblado y la ruta de acceso. También sugiere mitigaciones para evitar el uso del contexto de `LoadFrom`.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra una situación que puede activar este MDA:  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is
            // located outside of the Load context probing path.
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Diagnóstico de errores con asistentes para la depuración administrada](diagnosing-errors-with-managed-debugging-assistants.md)

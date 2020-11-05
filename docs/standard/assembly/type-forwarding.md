---
title: Reenvío de tipos en Common Language Runtime
description: El reenvío de tipos le permite mover un tipo a otro ensamblado sin tener que volver a compilar las aplicaciones que utilizan el ensamblado original.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: cd166068993fb5d1a5164615de3926a06dda8098
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687664"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Reenvío de tipos en Common Language Runtime

El reenvío de tipos le permite mover un tipo a otro ensamblado sin tener que volver a compilar las aplicaciones que utilizan el ensamblado original.  
  
 Por ejemplo, suponga que una aplicación utiliza la clase `Example` en un ensamblado denominado *Utility.dll*. Los desarrolladores de *Utility.dll* podrían decidir refactorizar el ensamblado y, en el proceso, podrían mover la clase `Example` a otro ensamblado. Si la versión anterior de *Utility.dll* se reemplaza por la nueva versión de *Utility.dll* y por su ensamblado complementario, la aplicación que usa la clase `Example` produce un error porque no puede encontrar la clase `Example` en la nueva versión de *Utility.dll*.  
  
 Los desarrolladores de *Utility.dll* pueden evitarlo mediante el reenvío de solicitudes para la clase `Example` con el atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>. Si se ha aplicado el atributo a la nueva versión de *Utility.dll* , las solicitudes para la clase `Example` se reenvían al ensamblado que contiene la clase. La aplicación existente continuará funcionando normalmente, sin necesidad de volver a compilarla.

## <a name="forward-a-type"></a>Reenvío de un tipo

 Hay cuatro pasos para reenviar un tipo:  
  
1. Traslade el código fuente del tipo desde el ensamblado original al ensamblado de destino.  

2. En el ensamblado en el que solía estar ubicado el tipo, agregue un atributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> para el tipo que se ha movido. El código siguiente muestra el atributo para un tipo denominado `Example` que se ha movido.  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. Compile el ensamblado que contiene el tipo ahora.  

4. Vuelva a compilar el ensamblado donde se encontraba antes el tipo, con una referencia al ensamblado que contiene el tipo ahora. Por ejemplo, si está compilando un archivo de C# desde la línea de comandos, utilice la opción [-reference (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) para especificar el ensamblado que contiene el tipo. En C++, utilice la directiva [#using](/cpp/preprocessor/hash-using-directive-cpp) en el archivo de código fuente para especificar el ensamblado que contiene el tipo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Reenvío de tipos (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [Directiva #using](/cpp/preprocessor/hash-using-directive-cpp)

---
title: Procedimiento para hacer referencia a un ensamblado con nombre seguro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 080d05a27b9e0b6ad4ff52d67ef8d9209dc1c697
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927953"
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Procedimiento para hacer referencia a un ensamblado con nombre seguro
El proceso para hacer referencia a tipos o recursos en un ensamblado con nombre seguro suele ser transparente. Puede hacer referencia en tiempo de compilación (enlace anticipado) o en tiempo de ejecución.  
  
 Una referencia en tiempo de compilación se produce cuando se le indica al compilador que el ensamblado hace referencia explícitamente a otro ensamblado. Cuando se usan referencias en tiempo de compilación, el compilador obtiene automáticamente la clave pública del ensamblado con nombre seguro de destino y la coloca en la referencia del ensamblado que se está compilando.  
  
> [!NOTE]
> Un ensamblado con nombre seguro solo puede usar tipos de otros ensamblados con nombre seguro. De lo contrario, se pondría en peligro la seguridad del ensamblado con nombre seguro.  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a>Para hacer referencia en tiempo de compilación a un ensamblado con nombre seguro  
  
1. En el símbolo del sistema, escriba el siguiente comando:  
  
     \<*compiler command*>  **/reference:** \<*assembly name*>  
  
     En este comando, *compiler command* es el comando del compilador para el lenguaje que está usando, y *assembly name* es el nombre del ensamblado con nombre seguro al que se hace referencia. También puede usar otras opciones de compilador, como la opción **/t:library** para crear un ensamblado de biblioteca.  
  
 En el ejemplo siguiente se crea un ensamblado denominado `myAssembly.dll` que hace referencia a un ensamblado con nombre seguro denominado `myLibAssembly.dll` desde un módulo de código denominado `myAssembly.cs`.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a>Para hacer referencia en tiempo de ejecución a un ensamblado con nombre seguro  
  
1. Cuando se hace referencia en tiempo de ejecución a un ensamblado con nombre seguro (por ejemplo, mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>), debe usar el nombre para mostrar del ensamblado con nombre seguro al que se hace referencia. La sintaxis de un nombre para mostrar es la siguiente:  
  
     \<*assembly name*> **,** \<*version number*> **,** \<*culture*> **,** \<*public key token*>  
  
     Por ejemplo:  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     En este ejemplo, `PublicKeyToken` es la forma hexadecimal del token de clave pública. Si no hay ningún valor de referencia cultural, use `Culture=neutral`.  
  
 En el ejemplo de código siguiente se muestra cómo usar esta información con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 Puede imprimir el formato hexadecimal de la clave pública y el token de clave pública de un ensamblado concreto. Para ello, use el siguiente comando de la [herramienta de nombre seguro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md):  
  
 **sn -Tp \<** *assembly* **>**  
  
 Si tiene un archivo de clave pública, puede usar en su lugar el comando siguiente (observe la diferencia en el caso de la opción de la línea de comandos):  
  
 **sn -tp \<** *archivo de clave pública* **>**  
  
## <a name="see-also"></a>Vea también

- [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

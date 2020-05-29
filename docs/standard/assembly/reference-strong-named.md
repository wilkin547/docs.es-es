---
title: Procedimiento para hacer referencia a un ensamblado con nombre seguro
description: En este artículo se muestra cómo hacer referencia a tipos o recursos en un ensamblado .NET con nombre seguro, en tiempo de compilación o en tiempo de ejecución.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: e42c1b461da16d7000605b9b9321138bbfebd307
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379876"
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Procedimiento para hacer referencia a un ensamblado con nombre seguro
El proceso para hacer referencia a tipos o recursos en un ensamblado con nombre seguro suele ser transparente. Puede hacer referencia en tiempo de compilación (enlace anticipado) o en tiempo de ejecución.  
  
Una referencia en tiempo de compilación se produce cuando se le indica al compilador que el ensamblado que se va a compilar hace referencia explícitamente a otro ensamblado. Cuando se usan referencias en tiempo de compilación, el compilador obtiene automáticamente la clave pública del ensamblado con nombre seguro de destino y la coloca en la referencia del ensamblado que se está compilando.
  
> [!NOTE]
> Un ensamblado con nombre seguro solo puede usar tipos de otros ensamblados con nombre seguro. De lo contrario, se pondría en peligro la seguridad del ensamblado con nombre seguro.  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a>Creación de una referencia en tiempo de compilación a un ensamblado con nombre seguro  

En un símbolo del sistema, escriba el siguiente comando:  

\<*compiler command*>  **/reference:** \<*assembly name*>  

En este comando, *compiler command* es el comando del compilador para el lenguaje que está usando, y *assembly name* es el nombre del ensamblado con nombre seguro al que se hace referencia. También puede usar otras opciones de compilador, como la opción **/t:library** para crear un ensamblado de biblioteca.  

En el ejemplo siguiente se crea un ensamblado denominado *myAssembly.dll* que hace referencia a un ensamblado con nombre seguro llamado *myLibAssembly.dll* desde el módulo de código *myAssembly.cs*.  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a>Creación de una referencia en tiempo de ejecución a un ensamblado con nombre seguro  
  
Cuando se crea una referencia en tiempo de ejecución a un ensamblado con nombre seguro (por ejemplo, mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>), debe usar el nombre para mostrar del ensamblado con nombre seguro al que se hace referencia. La sintaxis de un nombre para mostrar es la siguiente:  

\<*nombre del ensamblado*> **,** \<*número de versión*> **,** \<*referencia cultural*> **,** \<*token de clave pública*>  

Por ejemplo:  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

En este ejemplo, `PublicKeyToken` es la forma hexadecimal del token de clave pública. Si no hay ningún valor de referencia cultural, use `Culture=neutral`.  

En el ejemplo de código siguiente se muestra cómo usar esta información con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

Puede imprimir el formato hexadecimal de la clave pública y el token de clave pública de un ensamblado concreto. Para ello, use el siguiente comando de la [herramienta de nombre seguro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md):  

**sn -Tp \<** *ensamblado* **>**  

Si tiene un archivo de clave pública, puede usar en su lugar el comando siguiente (observe la diferencia en el caso de la opción de la línea de comandos):  

**sn -tp \<** *archivo de clave pública* **>**  

## <a name="see-also"></a>Vea también

- [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)

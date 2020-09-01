---
description: -target:module (Opciones del compilador de C#)
title: -target:module (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 2c592d2fe001bb0908a06a6eb3287a39040b8715
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128457"
---
# <a name="-targetmodule-c-compiler-options"></a>-target:module (Opciones del compilador de C#)
Esta opción hace que el compilador no genere un manifiesto del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Observaciones  
 De forma predeterminada, el archivo de salida creado al compilar con esta opción tendrá una extensión de .netmodule.  
  
 Common Language Runtime de .NET Framework no puede cargar un archivo que no tiene un manifiesto del ensamblado. En cambio, este archivo se puede incorporar en el manifiesto de un ensamblado mediante [-addmodule](./addmodule-compiler-option.md).  
  
 Si se crea más de un módulo en una única compilación, los tipos [internal](../keywords/internal.md) que haya en un módulo estarán disponibles para otros módulos de la compilación. Cuando el código de un módulo hace referencia a tipos `internal` de otro módulo, se deben incorporar ambos módulos en un manifiesto del ensamblado, mediante **-addmodule**.  
  
 No se admite la creación de un módulo en el entorno de desarrollo de Visual Studio.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compilación de `in.cs` y creación de `in.netmodule`:  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [-target (Opciones del compilador de C#)](./target-compiler-option.md)
- [Opciones del compilador de C#](./index.md)

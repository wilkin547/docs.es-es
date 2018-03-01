---
title: -codepage (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c1181ef98ac5f335c9737771eda2b3bd9227cc9f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-codepage-c-compiler-options"></a>-codepage (Opciones del compilador de C#)
Esta opción especifica qué página de códigos se va a usar durante la compilación si la página necesaria no es la página de códigos predeterminada actual del sistema.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumentos  
 `id`  
 El id. de la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.  
  
## <a name="remarks"></a>Comentarios  
 Si compila uno o más archivos de código fuente que no se han creado para usar la página de códigos predeterminada en su equipo, puede usar la opción **-codepage** para especificar qué página de códigos debe usarse. **-codepage** se aplica a todos los archivos de código fuente de su compilación.  
  
 Si los archivos de código fuente se han creado con la misma página de códigos que está en vigor en su equipo o si los archivos de código fuente se han creado con UNICODE o UTF-8, no necesita usar **-codepage**.  
  
 Vea [GetCPInfo](https://msdn.microsoft.com/library/dd318078(VS.85).aspx) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

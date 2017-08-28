---
title: -codepage (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a>/codepage (Opciones del compilador de C#)
Esta opción especifica qué página de códigos se va a usar durante la compilación si la página necesaria no es la página de códigos predeterminada actual del sistema.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a>Argumentos  
 `id`  
 El id. de la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.  
  
## <a name="remarks"></a>Comentarios  
 Si compila uno o más archivos de código fuente que no se han creado para usar la página de códigos predeterminada en su equipo, puede usar la opción **/codepage** para especificar qué página de códigos debe usarse. **/codepage** se aplica a todos los archivos de código fuente de su compilación.  
  
 Si los archivos de código fuente se han creado con la misma página de códigos que está en vigor en su equipo o si los archivos de código fuente se han creado con UNICODE o UTF-8, no necesita usar **/codepage**.  
  
 Vea [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)


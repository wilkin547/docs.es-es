---
title: -codepage (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 3352e7fc446ace391540360a3b6b36d604ca5f13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173762"
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
 El compilador primero intenta interpretar todos los archivos de código fuente como UTF-8. Si los archivos de código fuente se encuentran en una codificación distinta de UTF-8 y usan caracteres que no sean ASCII de 7 bits, emplee la opción **-codepage** para especificar qué página de códigos debe usarse. **-codepage** se aplica a todos los archivos de código fuente de su compilación.  

 Vea [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)

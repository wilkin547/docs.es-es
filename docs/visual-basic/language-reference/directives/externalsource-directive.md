---
title: '#<a name="externalsource-directive"></a>ExternalSource (directiva)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a>#ExternalSource (Directiva)
Indica una asignación entre líneas específicas de código fuente y texto externo al código fuente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Elementos  
 `StringLiteral`  
 La ruta de acceso del origen externo.  
  
 `IntLiteral`  
 El número de línea de la primera línea del origen externo.  
  
 `LogicalLine`  
 La línea donde se produce el error en el origen externo.  
  
 `#End ExternalSource`  
 Finaliza el bloque `#ExternalSource`.  
  
## <a name="remarks"></a>Comentarios  
 Esta directiva se usa únicamente por el compilador y el depurador.  
  
 Un archivo de código fuente puede incluir directivas de origen externo, lo que indica una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al código fuente, como un archivo .aspx. Si se producen errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.  
  
 Directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar. Están diseñados para uso interno por la aplicación únicamente.  
  
## <a name="see-also"></a>Vea también  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

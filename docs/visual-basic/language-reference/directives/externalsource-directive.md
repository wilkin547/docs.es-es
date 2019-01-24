---
title: '#ExternalSource (directiva) (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 550934723a5599573be578ce5746ab7520b59dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705974"
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
 La ruta de acceso para el origen externo.  
  
 `IntLiteral`  
 El número de línea de la primera línea del origen externo.  
  
 `LogicalLine`  
 La línea donde se produce el error en el origen externo.  
  
 `#End ExternalSource`  
 Finaliza el bloque `#ExternalSource`.  
  
## <a name="remarks"></a>Comentarios  
 Esta directiva se usa únicamente por el compilador y el depurador.  
  
 Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al código fuente, como un archivo .aspx. Si se producen errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.  
  
 Directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar. La aplicación solo están diseñados para uso interno.  
  
## <a name="see-also"></a>Vea también
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

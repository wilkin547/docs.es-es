---
title: '#Directiva ExternalSource'
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
ms.openlocfilehash: fa0a40827c1b3865b90c7d796ea4dd364774e1c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343828"
---
# <a name="externalsource-directive"></a>#ExternalSource (Directiva)

Indica una asignación entre líneas específicas de código fuente y texto externo al origen.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Elementos  

 `StringLiteral`  
 Ruta de acceso al origen externo.  
  
 `IntLiteral`  
 Número de línea de la primera línea del origen externo.  
  
 `LogicalLine`  
 La línea donde se produce el error en el origen externo.  
  
 `#End ExternalSource`  
 Finaliza el bloque `#ExternalSource`.  
  
## <a name="remarks"></a>Comentarios  

 Esta directiva solo la usan el compilador y el depurador.  
  
 Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al origen, como un archivo. aspx. Si se encuentran errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.  
  
 Las directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar. Están pensadas para uso interno de la aplicación únicamente.  
  
## <a name="see-also"></a>Vea también

- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

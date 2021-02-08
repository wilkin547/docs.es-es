---
description: 'Más información acerca de: Directiva de #ExternalSource'
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
ms.openlocfilehash: 1f2e73aa152fbe2d97edcde912626696faacd5af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797242"
---
# <a name="externalsource-directive"></a>#ExternalSource (Directiva)

Indica una asignación entre líneas específicas de código fuente y texto externo al origen.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Partes  

 `StringLiteral`  
 Ruta de acceso al origen externo.  
  
 `IntLiteral`  
 Número de línea de la primera línea del origen externo.  
  
 `LogicalLine`  
 La línea donde se produce el error en el origen externo.  
  
 `#End ExternalSource`  
 Finaliza el bloque `#ExternalSource`.  
  
## <a name="remarks"></a>Observaciones  

 Esta directiva solo la usan el compilador y el depurador.  
  
 Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas específicas de código en el archivo de código fuente y texto externo al origen, como un archivo. aspx. Si se encuentran errores en el código fuente designado durante la compilación, se identifican como procedentes del origen externo.  
  
 Las directivas de origen externo no tienen ningún efecto en la compilación y no se pueden anidar. Están pensadas para uso interno de la aplicación únicamente.  
  
## <a name="see-also"></a>Vea también

- [Compilación condicional](../../programming-guide/program-structure/conditional-compilation.md)

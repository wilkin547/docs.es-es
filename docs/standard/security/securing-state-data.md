---
title: Proteger los datos de estado
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe941fff7091fb579e41a3c417dbb2129bcf3e8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580788"
---
# <a name="securing-state-data"></a>Proteger los datos de estado
Las aplicaciones que administran datos confidenciales o realizan cualquier tipo de decisiones de seguridad necesitan mantener los datos bajo control y no pueden permitir que otro código potencialmente malintencionado acceda directamente a los datos. La mejor manera de proteger los datos en memoria es declarar los datos como variables privadas o internas (con el ámbito limitado al mismo ensamblado). Sin embargo, incluso estos datos están sujetos a acceso, por lo que debe tenerse en cuenta lo siguiente:  
  
-   Al usar mecanismos de reflexión, se puede obtener y establecer miembros privados en el código de plena confianza al que puede hacer referencia el objeto.  
  
-   Con la serialización, el código de plena confianza puede obtener y establecer eficazmente miembros privados si pueden acceder a los datos correspondientes en el formulario serializado del objeto.  
  
-   En la depuración, se pueden leer estos datos.  
  
 Asegúrese de que ninguno de sus métodos o propiedades expone estos valores de manera involuntaria.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)

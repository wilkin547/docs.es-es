---
title: Proteger los datos de estado
description: Declare los datos de estado como variables privadas o internas para limitar el acceso a ellos. Todavía se puede tener acceso a estos datos a través de la reflexión, la serialización y la depuración.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: 849ed993befaceda1b04becbb7fb2530c5c62a77
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824166"
---
# <a name="securing-state-data"></a>Proteger los datos de estado

Las aplicaciones que administran datos confidenciales o realizan cualquier tipo de decisiones de seguridad necesitan mantener los datos bajo control y no pueden permitir que otro código potencialmente malintencionado acceda directamente a los datos. La mejor manera de proteger los datos en memoria es declarar los datos como variables privadas o internas (con el ámbito limitado al mismo ensamblado). Sin embargo, incluso estos datos están sujetos a acceso, por lo que debe tenerse en cuenta lo siguiente:  
  
- Al usar mecanismos de reflexión, se puede obtener y establecer miembros privados en el código de plena confianza al que puede hacer referencia el objeto.  
  
- Con la serialización, el código de plena confianza puede obtener y establecer eficazmente miembros privados si pueden acceder a los datos correspondientes en el formulario serializado del objeto.  
  
- En la depuración, se pueden leer estos datos.  
  
 Asegúrese de que ninguno de sus métodos o propiedades expone estos valores de manera involuntaria.  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de codificación segura](secure-coding-guidelines.md)
- [Seguridad de ASP.NET Core](/aspnet/core/security/)

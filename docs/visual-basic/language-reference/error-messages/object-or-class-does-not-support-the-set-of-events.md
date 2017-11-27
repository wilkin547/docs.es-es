---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>El objeto o la clase no admite el conjunto de eventos
Se intentó usar un `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado. Por ejemplo, desea recibir los eventos de un objeto, a continuación, cree otro objeto que `Implements` el primer objeto. Aunque podría pensar que podría recibir los eventos del objeto implementado, esto no es siempre el caso. `Implements`sólo implementa una interfaz para los métodos y propiedades. `WithEvents`no se admite para privada `UserControls`, porque el tipo de información necesaria para generar el `ObjectEvent` no está disponible en tiempo de ejecución.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  No puede recibir eventos para un componente que no del origen de eventos.  
  
## <a name="see-also"></a>Vea también  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)

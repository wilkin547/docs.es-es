---
title: "El procedimiento Let de la propiedad no está definido y el procedimiento Get no ha devuelto un objeto"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b043ca698a9c90afd41de90c7dbc5879ae7de623
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>El procedimiento Let de la propiedad no está definido y el procedimiento Get no ha devuelto un objeto
Ciertas operaciones, métodos y propiedades solo se pueden aplicar a `Collection` objetos. Ha especificado una operación o propiedad que es exclusiva para colecciones, pero el objeto no es una colección.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe la ortografía del nombre del objeto o una propiedad, o compruebe que el objeto es un `Collection` objeto.  
  
2.  Mire el `Add` método usado para agregar el objeto a la colección para estar seguro de que la sintaxis es correcta y que se han escrito correctamente los identificadores.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Collection>

---
title: La variable utiliza un tipo de Automation no compatible con Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8798b2cedb295a05133ef08c22110a68bc3158a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic
Se intentó utilizar una variable definida en una biblioteca de tipos o la biblioteca de objetos que tiene un tipo de datos no admitido por [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Utilizar una variable de un tipo reconocido por [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
     O bien  
  
-   Si se produce este error durante el uso de `FileGet` o `FileGetOBject`, asegúrese de que el archivo que está intentando usar se escribió con `FilePut` o `FilePutObject`.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)

---
title: "Cómo: compartir un ensamblado con otras aplicaciones (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8065a66c8f7c7b9ccb9125b060b0c03cde273482
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Cómo: compartir un ensamblado con otras aplicaciones (Visual Basic)
Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se han diseñado para ser utilizados por otras aplicaciones.  
  
 Para compartir un ensamblado con otras aplicaciones, debe colocarse en el [caché Global de ensamblados](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).  
  
### <a name="sharing-an-assembly"></a>Compartir un ensamblado  
  
1.  Cree el ensamblado. Para obtener más información, consulte [crear ensamblados](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).  
  
2.  Asignar un nombre seguro al ensamblado. Para obtener más información, consulte [Cómo: firmar un ensamblado con un nombre seguro](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).  
  
3.  Asigne la información de versión al ensamblado. Para obtener más información, consulte [versiones del ensamblado](https://msdn.microsoft.com/library/51ket42z).  
  
4.  Agregue el ensamblado a la caché de ensamblados Global. Para obtener más información, consulte [Cómo: instalar un ensamblado en la caché de ensamblados Global](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).  
  
5.  Obtener acceso a los tipos contenidos en el ensamblado de las otras aplicaciones. Para obtener más información, consulte [Cómo: hacer referencia a un ensamblado con nombre seguro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
 [ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Programar con ensamblados](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)

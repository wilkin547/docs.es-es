---
title: "Cómo: Escribir mensajes de registro (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a340c807707cb63d20c8186a8ec6f81830f1a9ed
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-write-log-messages-visual-basic"></a>Cómo: Escribir mensajes de registro (Visual Basic)
Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre su aplicación. Este ejemplo muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento.  
  
 Para registrar información de la excepción, use el método `My.Application.Log.WriteException`; vea [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el método `My.Application.Log.WriteEntry` para escribir la información de seguimiento.  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Asegúrese de que los datos que se escribe en el registro no incluyen información confidencial, como contraseñas de usuario. Para obtener más información, vea [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Tutorial: Cambiar el lugar donde My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)

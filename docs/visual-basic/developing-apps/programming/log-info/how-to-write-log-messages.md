---
title: Procedimiento para escribir mensajes de registro (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: c12d0cde7d8128400769cd2e93361bb10e08f59b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967027"
---
# <a name="how-to-write-log-messages-visual-basic"></a>Procedimiento para escribir mensajes de registro (Visual Basic)
Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre su aplicación. Este ejemplo muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento.  
  
 Para obtener información sobre el registro de excepciones, use el método `My.Application.Log.WriteException`; vea [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el método `My.Application.Log.WriteEntry` para escribir la información de seguimiento.  
  
 [!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Asegúrese de que los datos que se escribe en el registro no incluyen información confidencial, como contraseñas de usuario. Para obtener más información, vea [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)

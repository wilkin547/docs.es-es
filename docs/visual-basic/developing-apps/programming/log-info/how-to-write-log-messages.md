---
title: 'Cómo: Escribir mensajes de registro'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 28c5fe77e2711dfcac96e621a90fb9506eb74775
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410054"
---
# <a name="how-to-write-log-messages-visual-basic"></a>Cómo: Escribir mensajes de registro (Visual Basic)

Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre su aplicación. Este ejemplo muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento.

Para registrar información de la excepción, use el método `My.Application.Log.WriteException`; vea [Cómo: Registrar excepciones](how-to-log-exceptions.md).

## <a name="example"></a>Ejemplo

En este ejemplo se usa el método `My.Application.Log.WriteEntry` para escribir la información de seguimiento.

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a>Seguridad de .NET Framework

Asegúrese de que los datos que se escribe en el registro no incluyen información confidencial, como contraseñas de usuario. Para obtener más información, vea [Trabajar con registros de aplicaciones](working-with-application-logs.md).

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Trabajar con registros de aplicaciones](working-with-application-logs.md)
- [Registrar excepciones](how-to-log-exceptions.md)
- [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](walkthrough-determining-where-my-application-log-writes-information.md)
- [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](walkthrough-changing-where-my-application-log-writes-information.md)
- [Tutorial: Filtrar el resultado de My.Application.Log](walkthrough-filtering-my-application-log-output.md)

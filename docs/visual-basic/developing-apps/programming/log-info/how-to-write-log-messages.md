---
title: Procedimiento para escribir mensajes de registro (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 4b4210983aa5bd57f1b0a89f2f06f089e98670f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594956"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="fb524-102">Procedimiento para escribir mensajes de registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb524-102">How to: Write Log Messages (Visual Basic)</span></span>
<span data-ttu-id="fb524-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre su aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb524-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="fb524-104">Este ejemplo muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fb524-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>  
  
 <span data-ttu-id="fb524-105">Para obtener información sobre el registro de excepciones, use el método `My.Application.Log.WriteException`; vea [Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="fb524-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb524-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb524-106">Example</span></span>  
 <span data-ttu-id="fb524-107">En este ejemplo se usa el método `My.Application.Log.WriteEntry` para escribir la información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fb524-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="fb524-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fb524-108">.NET Framework Security</span></span>  
 <span data-ttu-id="fb524-109">Asegúrese de que los datos que se escribe en el registro no incluyen información confidencial, como contraseñas de usuario.</span><span class="sxs-lookup"><span data-stu-id="fb524-109">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="fb524-110">Para obtener más información, vea [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="fb524-110">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb524-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb524-111">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="fb524-112">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fb524-112">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="fb524-113">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="fb524-113">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="fb524-114">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="fb524-114">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="fb524-115">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="fb524-115">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="fb524-116">Tutorial: Filtrar el resultado de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="fb524-116">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)

---
description: 'Más información acerca de: Procedimiento: para escribir mensajes de registro (Visual Basic)'
title: Procedimiento para escribir mensajes de registro
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: ed455fdb2cebda908981514bef932942adf499ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797307"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="5a0d0-103">Cómo: Escribir mensajes de registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a0d0-103">How to: Write Log Messages (Visual Basic)</span></span>

<span data-ttu-id="5a0d0-104">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a0d0-104">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="5a0d0-105">Este ejemplo muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5a0d0-105">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>

<span data-ttu-id="5a0d0-106">Para registrar información de la excepción, use el método `My.Application.Log.WriteException`; vea [Cómo: Registrar excepciones](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="5a0d0-106">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

## <a name="example"></a><span data-ttu-id="5a0d0-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a0d0-107">Example</span></span>

<span data-ttu-id="5a0d0-108">En este ejemplo se usa el método `My.Application.Log.WriteEntry` para escribir la información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5a0d0-108">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a><span data-ttu-id="5a0d0-109">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a0d0-109">.NET Framework Security</span></span>

<span data-ttu-id="5a0d0-110">Asegúrese de que los datos que se escribe en el registro no incluyen información confidencial, como contraseñas de usuario.</span><span class="sxs-lookup"><span data-stu-id="5a0d0-110">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="5a0d0-111">Para obtener más información, vea [Trabajar con registros de aplicaciones](working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="5a0d0-111">For more information, see [Working with Application Logs](working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a0d0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a0d0-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="5a0d0-113">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="5a0d0-113">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="5a0d0-114">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="5a0d0-114">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="5a0d0-115">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="5a0d0-115">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="5a0d0-116">Tutorial: Cambiar el lugar donde My.Application.Log escribe información</span><span class="sxs-lookup"><span data-stu-id="5a0d0-116">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="5a0d0-117">Tutorial: Filtrar el resultado de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="5a0d0-117">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)

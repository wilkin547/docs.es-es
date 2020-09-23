---
title: Procedimiento apara llamar a un procedimiento que no devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 2686a4d9dc10cde209f558771feeb5ba4f4ccb21
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075010"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="bfa9f-102">Cómo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfa9f-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>

<span data-ttu-id="bfa9f-103">Un `Sub` procedimiento no devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="bfa9f-104">Se llama explícitamente con una instrucción de llamada independiente.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="bfa9f-105">No se puede llamar simplemente mediante su nombre en una expresión.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="bfa9f-106">Para llamar a un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="bfa9f-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="bfa9f-107">Especifique el nombre del `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="bfa9f-108">Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="bfa9f-109">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="bfa9f-110">Sin embargo, el uso de los paréntesis facilita la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="bfa9f-111">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="bfa9f-112">Asegúrese de proporcionar los argumentos en el mismo orden en que el `Sub` procedimiento define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="bfa9f-113">En el ejemplo siguiente se llama <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> a la función Visual Basic para activar una ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="bfa9f-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> toma el título de la ventana como su único argumento.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="bfa9f-115">No devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="bfa9f-116">Si no se está ejecutando un proceso del Bloc de notas, el ejemplo produce una excepción <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="bfa9f-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="bfa9f-117">`Shell`En el procedimiento se supone que las aplicaciones están en las rutas de acceso especificadas.</span><span class="sxs-lookup"><span data-stu-id="bfa9f-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="bfa9f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfa9f-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="bfa9f-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="bfa9f-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bfa9f-120">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="bfa9f-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="bfa9f-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="bfa9f-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bfa9f-122">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="bfa9f-122">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="bfa9f-123">Procedimiento para crear un procedimiento</span><span class="sxs-lookup"><span data-stu-id="bfa9f-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="bfa9f-124">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="bfa9f-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="bfa9f-125">Cómo: Llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfa9f-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)

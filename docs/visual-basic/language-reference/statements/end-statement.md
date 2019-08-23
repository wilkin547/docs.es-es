---
title: End (instrucción Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944465"
---
# <a name="end-statement"></a><span data-ttu-id="89d8e-102">End (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="89d8e-102">End Statement</span></span>
<span data-ttu-id="89d8e-103">Finaliza la ejecución inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="89d8e-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89d8e-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="89d8e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89d8e-105">Remarks</span></span>  
 <span data-ttu-id="89d8e-106">Puede colocar la `End` instrucción en cualquier parte de un procedimiento para obligar a que toda la aplicación deje de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="89d8e-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="89d8e-107">`End`cierra los archivos abiertos con una `Open` instrucción y borra todas las variables de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="89d8e-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="89d8e-108">La aplicación se cierra en cuanto no hay ningún otro programa que contenga referencias a sus objetos y no se está ejecutando ningún código.</span><span class="sxs-lookup"><span data-stu-id="89d8e-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89d8e-109">La `End` instrucción detiene la ejecución del código repentinamente y no invoca el `Dispose` método `Finalize` o, ni ningún otro código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="89d8e-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="89d8e-110">Se invalidan las referencias de objeto mantenidas por otros programas.</span><span class="sxs-lookup"><span data-stu-id="89d8e-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="89d8e-111">Si se `End` encuentra una instrucción dentro de `Try` un `Catch` bloque o, el control no pasa al bloque `Finally` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="89d8e-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="89d8e-112">La `Stop` instrucción suspende la ejecución, pero, a `End`diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.</span><span class="sxs-lookup"><span data-stu-id="89d8e-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="89d8e-113">Dado `End` que finaliza la aplicación sin tener que ocuparse de los recursos que puedan estar abiertos, debe intentar cerrarlo correctamente antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="89d8e-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="89d8e-114">Por ejemplo, si la aplicación tiene algún formulario abierto, debe cerrarlo antes de que el control `End` alcance la instrucción.</span><span class="sxs-lookup"><span data-stu-id="89d8e-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="89d8e-115">Debería usar `End` con moderación y solo cuando necesite detenerse inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="89d8e-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="89d8e-116">Las formas normales de finalizar un procedimiento ([instrucción return](../../../visual-basic/language-reference/statements/return-statement.md) y de [salida](../../../visual-basic/language-reference/statements/exit-statement.md)) no solo cierran el procedimiento correctamente, sino que también proporcionan al código de llamada la oportunidad de cerrarse sin problemas.</span><span class="sxs-lookup"><span data-stu-id="89d8e-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="89d8e-117">Por ejemplo, una aplicación de consola puede simplemente `Return` `Main` del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="89d8e-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="89d8e-118">La `End` instrucción llama al <xref:System.Environment.Exit%2A> método de la <xref:System.Environment> clase en el <xref:System> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="89d8e-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="89d8e-119"><xref:System.Environment.Exit%2A>requiere que tenga `UnmanagedCode` permiso.</span><span class="sxs-lookup"><span data-stu-id="89d8e-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="89d8e-120">Si no lo hace, se <xref:System.Security.SecurityException> produce un error.</span><span class="sxs-lookup"><span data-stu-id="89d8e-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="89d8e-121">Cuando va seguido de una palabra clave adicional, la [palabra clave end \<> instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) define el final de la definición del procedimiento o bloque adecuado.</span><span class="sxs-lookup"><span data-stu-id="89d8e-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="89d8e-122">Por ejemplo, `End Function` finaliza la definición de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="89d8e-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89d8e-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89d8e-123">Example</span></span>  
 <span data-ttu-id="89d8e-124">En el ejemplo siguiente se `End` usa la instrucción para finalizar la ejecución del código si el usuario lo solicita.</span><span class="sxs-lookup"><span data-stu-id="89d8e-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="89d8e-125">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="89d8e-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="89d8e-126">Esta instrucción no se admite.</span><span class="sxs-lookup"><span data-stu-id="89d8e-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d8e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="89d8e-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="89d8e-128">Stop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="89d8e-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="89d8e-129">End \<keyword > instrucción</span><span class="sxs-lookup"><span data-stu-id="89d8e-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)

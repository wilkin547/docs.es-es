---
title: End (instrucción) (Visual Basic)
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
ms.openlocfilehash: a2c211e5ebfd00a639644243312cbe25f71f4cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593711"
---
# <a name="end-statement"></a><span data-ttu-id="4207f-102">End (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="4207f-102">End Statement</span></span>
<span data-ttu-id="4207f-103">Finaliza la ejecución inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4207f-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4207f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4207f-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="4207f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4207f-105">Remarks</span></span>  
 <span data-ttu-id="4207f-106">Puede colocar el `End` instrucción en cualquier parte de un procedimiento para forzar la aplicación completa para detener la ejecución.</span><span class="sxs-lookup"><span data-stu-id="4207f-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="4207f-107">`End` cierra los archivos abiertos con un `Open` instrucción y borra todas las variables de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4207f-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="4207f-108">La aplicación se cierra en cuanto no hay ningún otro programa que contiene referencias a sus objetos y ninguna de su código se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4207f-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4207f-109">El `End` instrucción detiene la ejecución de código repentinamente y no invoca el `Dispose` o `Finalize` método, o cualquier otro código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4207f-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="4207f-110">Se invalidan las referencias de objeto mantenidas por otros programas.</span><span class="sxs-lookup"><span data-stu-id="4207f-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="4207f-111">Si un `End` instrucción se encuentra dentro de un `Try` o `Catch` bloque de control no pasa a la correspondiente `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="4207f-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="4207f-112">El `Stop` instrucción suspende la ejecución, pero, a diferencia `End`, no cierre los archivos ni borrar las variables, a menos que se encuentre en un archivo ejecutable compilado (.exe).</span><span class="sxs-lookup"><span data-stu-id="4207f-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="4207f-113">Dado que `End` finaliza su aplicación sin tener a los recursos que estén abiertos, debe intentar cerrarse limpiamente antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="4207f-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="4207f-114">Por ejemplo, si la aplicación tiene formularios abiertos, debe cerrarlos antes de control alcanza el `End` instrucción.</span><span class="sxs-lookup"><span data-stu-id="4207f-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="4207f-115">Debe usar `End` con moderación y solo cuando sea necesario detener inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4207f-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="4207f-116">Las formas para finalizar un procedimiento normales ([instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) y [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) no sólo cierran el procedimiento limpiamente, pero también proporcionar el código que realiza la llamada la oportunidad de cerrarse limpiamente.</span><span class="sxs-lookup"><span data-stu-id="4207f-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="4207f-117">Una aplicación de consola, por ejemplo, puede simplemente `Return` desde el `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4207f-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4207f-118">El `End` instrucción llama a la <xref:System.Environment.Exit%2A> método de la <xref:System.Environment> clase en el <xref:System> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4207f-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="4207f-119"><xref:System.Environment.Exit%2A> requiere que haya `UnmanagedCode` permiso.</span><span class="sxs-lookup"><span data-stu-id="4207f-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="4207f-120">Si no, un <xref:System.Security.SecurityException> se produce el error.</span><span class="sxs-lookup"><span data-stu-id="4207f-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="4207f-121">Cuando va seguido de una palabra clave adicional, [final \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delimita el final de la definición del procedimiento apropiado o bloque.</span><span class="sxs-lookup"><span data-stu-id="4207f-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="4207f-122">Por ejemplo, `End Function` termina la definición de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4207f-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4207f-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4207f-123">Example</span></span>  
 <span data-ttu-id="4207f-124">En el ejemplo siguiente se usa el `End` instrucción para finalizar la ejecución de código si el usuario lo solicita.</span><span class="sxs-lookup"><span data-stu-id="4207f-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="4207f-125">Notas de desarrollador de dispositivos inteligentes</span><span class="sxs-lookup"><span data-stu-id="4207f-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="4207f-126">No se admite esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="4207f-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4207f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4207f-127">See also</span></span>
- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="4207f-128">Stop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4207f-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="4207f-129">End \<palabra clave > instrucción</span><span class="sxs-lookup"><span data-stu-id="4207f-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)

---
title: /errorreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0abe276aaacdeb175c3af7067dffa81448450e22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="errorreport"></a><span data-ttu-id="fec26-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="fec26-102">/errorreport</span></span>
<span data-ttu-id="fec26-103">Especifica cómo debe documentar el compilador [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] los errores internos del compilador.</span><span class="sxs-lookup"><span data-stu-id="fec26-103">Specifies how the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fec26-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="fec26-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fec26-105">Remarks</span></span>  
 <span data-ttu-id="fec26-106">Esta opción proporciona una manera cómoda para informes un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] error del compilador interno (ICE) a la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] equipo de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] team at Microsoft.</span></span> <span data-ttu-id="fec26-107">De forma predeterminada, el compilador no envía ninguna información a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="fec26-108">Sin embargo, si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="fec26-109">Esta información le ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la siguiente versión de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fec26-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="fec26-110">Capacidad de un usuario para enviar informes depende de los permisos de directiva de equipo y de usuario.</span><span class="sxs-lookup"><span data-stu-id="fec26-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="fec26-111">En la tabla siguiente se resume el efecto de la `/errorreport` opción.</span><span class="sxs-lookup"><span data-stu-id="fec26-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="fec26-112">Opción</span><span class="sxs-lookup"><span data-stu-id="fec26-112">Option</span></span>|<span data-ttu-id="fec26-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="fec26-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="fec26-114">Si se produce un error interno del compilador, aparece un cuadro de diálogo para que pueda ver los datos exactos que recogidos por el compilador.</span><span class="sxs-lookup"><span data-stu-id="fec26-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="fec26-115">Puede determinar si hay cualquier información confidencial en el informe de errores y tomar una decisión sobre si se envía a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="fec26-116">Si decide enviarlo, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="fec26-117">Pone en cola el informe de error.</span><span class="sxs-lookup"><span data-stu-id="fec26-117">Queues the error report.</span></span> <span data-ttu-id="fec26-118">Cuando inicia una sesión con privilegios de administrador, puede notificar los errores desde la última vez que se ha iniciado sesión (no se le pedirá que envíe informes de errores más de una vez cada tres días).</span><span class="sxs-lookup"><span data-stu-id="fec26-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="fec26-119">Éste es el comportamiento predeterminado cuando la `/errorreport` no se especifica la opción.</span><span class="sxs-lookup"><span data-stu-id="fec26-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="fec26-120">Si se produce un error interno del compilador y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="fec26-121">La opción `/errorReport:send` intenta enviar automáticamente información de errores a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="fec26-122">Esta opción depende del registro.</span><span class="sxs-lookup"><span data-stu-id="fec26-122">This option depends on the registry.</span></span> <span data-ttu-id="fec26-123">Para obtener más información acerca de cómo establecer los valores apropiados en el registro, consulte [cómo activar informe de errores automático en herramientas de línea de comandos de Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="fec26-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="fec26-124">Si se produce un error interno del compilador, no se recopila o envía a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="fec26-125">El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente.</span><span class="sxs-lookup"><span data-stu-id="fec26-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="fec26-126">Si `/errorreport` se utiliza con la [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, se envía el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fec26-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="fec26-127">Esta opción se utiliza con la [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, porque permite que los ingenieros de Microsoft a más fácilmente reproducen el error.</span><span class="sxs-lookup"><span data-stu-id="fec26-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fec26-128">El `/errorreport` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fec26-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fec26-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fec26-129">Example</span></span>  
 <span data-ttu-id="fec26-130">El código siguiente intenta compilar `T2.vb`, y si el compilador encuentra un error interno del compilador, solicita si desea enviar el informe de errores a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fec26-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fec26-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fec26-131">See Also</span></span>  
 [<span data-ttu-id="fec26-132">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fec26-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="fec26-133">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fec26-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="fec26-134">/bugreport</span><span class="sxs-lookup"><span data-stu-id="fec26-134">/bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)

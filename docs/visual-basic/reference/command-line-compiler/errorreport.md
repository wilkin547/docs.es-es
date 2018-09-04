---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509678"
---
# <a name="-errorreport"></a><span data-ttu-id="9f6dc-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="9f6dc-102">-errorreport</span></span>

<span data-ttu-id="9f6dc-103">Especifica cómo el compilador de Visual Basic debe notificar errores internos del compilador.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f6dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f6dc-104">Syntax</span></span>

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="9f6dc-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f6dc-105">Remarks</span></span>

<span data-ttu-id="9f6dc-106">Esta opción proporciona una forma cómoda para notificar un error interno del compilador de Visual Basic (ICE) al equipo de Visual Basic a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="9f6dc-107">De forma predeterminada, el compilador no envía ninguna información a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="9f6dc-108">Sin embargo, si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="9f6dc-109">Esta información le ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la próxima versión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="9f6dc-110">Capacidad de un usuario para enviar informes depende de los permisos de directiva de equipo y usuario.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="9f6dc-111">En la tabla siguiente se resume el efecto de la `-errorreport` opción.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="9f6dc-112">Opción</span><span class="sxs-lookup"><span data-stu-id="9f6dc-112">Option</span></span>|<span data-ttu-id="9f6dc-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="9f6dc-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="9f6dc-114">Si se produce un error interno del compilador, aparece un cuadro de diálogo para que pueda ver los datos exactos que el compilador recopilado.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="9f6dc-115">Puede determinar si no hay ninguna información confidencial en el informe de errores y tomar una decisión sobre si se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="9f6dc-116">Si decide que debe enviarla, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="9f6dc-117">Pone en cola el informe de error.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-117">Queues the error report.</span></span> <span data-ttu-id="9f6dc-118">Cuando inicie sesión con privilegios de administrador, puede notificar los errores desde la última vez que se ha iniciado sesión (no se le indicará que envíe informes de errores más de una vez cada tres días).</span><span class="sxs-lookup"><span data-stu-id="9f6dc-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="9f6dc-119">Este es el comportamiento predeterminado cuando el `-errorreport` no se especifica la opción.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="9f6dc-120">Si se produce un error interno del compilador, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="9f6dc-121">La opción `-errorreport:send` intenta enviar automáticamente información de errores a Microsoft si el informe está habilitado por la [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="9f6dc-122">Si se produce un error interno del compilador, no se recopila o envía a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="9f6dc-123">El compilador envía los datos que incluyen la pila en el momento del error, que normalmente incluye código fuente.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="9f6dc-124">Si `-errorreport` se usa con el [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, se envía el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="9f6dc-125">Esta opción se usa mejor con la [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, ya que permite a los ingenieros de Microsoft más fácil reproducen el error.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="9f6dc-126">El `-errorreport` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="9f6dc-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f6dc-127">Example</span></span>

<span data-ttu-id="9f6dc-128">El código siguiente intenta compilar `T2.vb`, y si el compilador encuentra un error interno del compilador, pregunta si desea enviar el informe de errores a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f6dc-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="9f6dc-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f6dc-129">See also</span></span>

- [<span data-ttu-id="9f6dc-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f6dc-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9f6dc-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f6dc-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="9f6dc-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="9f6dc-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)

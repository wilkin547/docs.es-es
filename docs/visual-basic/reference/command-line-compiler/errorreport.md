---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775671"
---
# <a name="-errorreport"></a><span data-ttu-id="6e197-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="6e197-102">-errorreport</span></span>

<span data-ttu-id="6e197-103">Especifica cómo el compilador de Visual Basic debe informar de los errores internos del compilador.</span><span class="sxs-lookup"><span data-stu-id="6e197-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e197-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e197-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="6e197-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e197-105">Remarks</span></span>

<span data-ttu-id="6e197-106">Esta opción proporciona una manera cómoda de notificar un Visual Basic error interno del compilador (ICE) al equipo de Visual Basic en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="6e197-107">De forma predeterminada, el compilador no envía información a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="6e197-108">Sin embargo, si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="6e197-109">Esa información ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la próxima versión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6e197-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="6e197-110">La capacidad de un usuario para enviar informes depende de los permisos de directiva de usuario y equipo.</span><span class="sxs-lookup"><span data-stu-id="6e197-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="6e197-111">En la tabla siguiente se resume el efecto de la opción `-errorreport`.</span><span class="sxs-lookup"><span data-stu-id="6e197-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="6e197-112">Opción</span><span class="sxs-lookup"><span data-stu-id="6e197-112">Option</span></span>|<span data-ttu-id="6e197-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="6e197-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="6e197-114">Si se produce un error interno del compilador, se abre un cuadro de diálogo para que pueda ver los datos exactos recopilados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="6e197-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="6e197-115">Puede determinar si hay información confidencial en el informe de errores y tomar una decisión sobre si se debe enviar a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="6e197-116">Si decide enviarlo, y el equipo y la configuración de la Directiva de usuario lo permiten, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="6e197-117">Pone en cola el informe de error.</span><span class="sxs-lookup"><span data-stu-id="6e197-117">Queues the error report.</span></span> <span data-ttu-id="6e197-118">Cuando inicie sesión con privilegios de administrador, puede informar de los errores desde la última vez que inició sesión (no se le pedirá que envíe informes de errores más de una vez cada tres días).</span><span class="sxs-lookup"><span data-stu-id="6e197-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="6e197-119">Éste es el comportamiento predeterminado cuando no se especifica la opción `-errorreport`.</span><span class="sxs-lookup"><span data-stu-id="6e197-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="6e197-120">Si se produce un error interno del compilador y el equipo y la configuración de la Directiva de usuario lo permiten, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="6e197-121">La opción `-errorreport:send` intenta enviar automáticamente información de errores a Microsoft si los informes están habilitados por la configuración del sistema [Informe de errores de Windows](/windows/desktop/wer/windows-error-reporting) .</span><span class="sxs-lookup"><span data-stu-id="6e197-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="6e197-122">Si se produce un error interno del compilador, no se recopilará ni se enviará a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="6e197-123">El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente.</span><span class="sxs-lookup"><span data-stu-id="6e197-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="6e197-124">Si `-errorreport` se usa con la opción [-bugreport (](../../../visual-basic/reference/command-line-compiler/bugreport.md) , se envía el archivo de código fuente completo.</span><span class="sxs-lookup"><span data-stu-id="6e197-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="6e197-125">Esta opción se utiliza mejor con la opción [-bugreport (](../../../visual-basic/reference/command-line-compiler/bugreport.md) , ya que permite a los ingenieros de Microsoft reproducir el error más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="6e197-125">This option is best used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="6e197-126">La opción `-errorreport` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6e197-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="6e197-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e197-127">Example</span></span>

<span data-ttu-id="6e197-128">El código siguiente intenta compilar `T2.vb` y, si el compilador encuentra un error interno del compilador, le pedirá que envíe el informe de errores a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e197-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="6e197-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e197-129">See also</span></span>

- [<span data-ttu-id="6e197-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e197-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6e197-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e197-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6e197-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="6e197-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)

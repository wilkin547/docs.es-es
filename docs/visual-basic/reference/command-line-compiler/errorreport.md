---
description: Mas información sobre -errorreport
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6fa10482e6852a819303074b4662f02eb8d1f88
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475947"
---
# <a name="-errorreport"></a><span data-ttu-id="4d1a0-103">-errorreport</span><span class="sxs-lookup"><span data-stu-id="4d1a0-103">-errorreport</span></span>

<span data-ttu-id="4d1a0-104">Especifica cómo debe documentar el compilador de Visual Basic los errores internos del compilador.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-104">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d1a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d1a0-105">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="4d1a0-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d1a0-106">Remarks</span></span>

<span data-ttu-id="4d1a0-107">Esta opción ofrece una manera cómoda de notificar un error interno del compilador (ICE) de Visual Basic al equipo de Visual Basic en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-107">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="4d1a0-108">De forma predeterminada, el compilador no envía ninguna información a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-108">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="4d1a0-109">Aunque si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-109">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="4d1a0-110">Esa información ayudará a los ingenieros de Microsoft a identificar la causa y puede que ayude a mejorar la próxima versión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-110">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="4d1a0-111">La capacidad de un usuario de enviar informes depende de los permisos de las directivas de máquina y de usuario.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-111">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="4d1a0-112">En la siguiente tabla se resumen los efectos de la opción `-errorreport`.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-112">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="4d1a0-113">Opción</span><span class="sxs-lookup"><span data-stu-id="4d1a0-113">Option</span></span>|<span data-ttu-id="4d1a0-114">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="4d1a0-114">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="4d1a0-115">Si se produce un error interno del compilador, se abre un cuadro de diálogo para que pueda ver los datos exactos recopilados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-115">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="4d1a0-116">Puede determinar si hay información confidencial en el informe de errores y tomar una decisión sobre si se debe enviar a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-116">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="4d1a0-117">Si decide enviarlo y la configuración de las directivas de máquina y de usuario lo permite, el compilador enviará los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-117">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="4d1a0-118">Pone en cola el informe de error.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-118">Queues the error report.</span></span> <span data-ttu-id="4d1a0-119">Cuando inicie sesión con privilegios de administrador, puede informar de los errores desde la última vez que inició sesión (no se le pedirá que envíe informes de errores más de una vez cada tres días).</span><span class="sxs-lookup"><span data-stu-id="4d1a0-119">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="4d1a0-120">Se trata del comportamiento predeterminado cuando no se especifica la opción `-errorreport`.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-120">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="4d1a0-121">Si se produce un error interno del compilador y la configuración de las directivas de máquina y de usuario lo permite, el compilador envía los datos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-121">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="4d1a0-122">La opción `-errorreport:send` intenta enviar automáticamente información de errores a Microsoft si los informes se han habilitado en la configuración del sistema del [Informe de errores de Windows](/windows/desktop/wer/windows-error-reporting).</span><span class="sxs-lookup"><span data-stu-id="4d1a0-122">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="4d1a0-123">Si se produce un error interno del compilador, no se recopilará ni se enviará a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-123">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="4d1a0-124">El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-124">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="4d1a0-125">Si se usa `-errorreport` con la opción [-bugreport](bugreport.md), se envía el archivo de origen completo.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-125">If `-errorreport` is used with the [-bugreport](bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="4d1a0-126">Esta opción se utiliza mejor con la opción [-bugreport](bugreport.md), ya que permite a los ingenieros de Microsoft reproducir más fácilmente el error.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-126">This option is best used with the [-bugreport](bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="4d1a0-127">La opción `-errorreport` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-127">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="4d1a0-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d1a0-128">Example</span></span>

<span data-ttu-id="4d1a0-129">El código siguiente intenta compilar `T2.vb` y, si el compilador encuentra un error interno del compilador, le pedirá que envíe el informe de errores a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d1a0-129">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="4d1a0-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d1a0-130">See also</span></span>

- [<span data-ttu-id="4d1a0-131">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d1a0-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="4d1a0-132">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d1a0-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="4d1a0-133">-bugreport</span><span class="sxs-lookup"><span data-stu-id="4d1a0-133">-bugreport</span></span>](bugreport.md)

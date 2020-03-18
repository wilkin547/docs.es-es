---
title: -errorreport (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 52b58aac5e82d4228dfda9c4d77c1d1c5de3e0cd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253894"
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="976f0-102">-errorreport (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="976f0-102">-errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="976f0-103">Esta opción proporciona una forma cómoda de notificar un error interno del compilador de C# a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="976f0-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="976f0-104">En Windows Vista y Windows Server 2008, la configuración de informes de errores para Visual Studio no reemplaza la configuración realizada a través de Informe de errores de Windows (WER).</span><span class="sxs-lookup"><span data-stu-id="976f0-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="976f0-105">La configuración de WER siempre tiene prioridad sobre la configuración de informes de errores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="976f0-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>

## <a name="syntax"></a><span data-ttu-id="976f0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="976f0-106">Syntax</span></span>

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a><span data-ttu-id="976f0-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="976f0-107">Arguments</span></span>
 <span data-ttu-id="976f0-108">**none**</span><span class="sxs-lookup"><span data-stu-id="976f0-108">**none**</span></span>  
 <span data-ttu-id="976f0-109">No se recopilarán informes sobre errores internos del compilador ni se enviarán a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="976f0-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>

 <span data-ttu-id="976f0-110">**prompt**: pregunta si desea enviar un informe cuando recibe un error interno del compilador.</span><span class="sxs-lookup"><span data-stu-id="976f0-110">**prompt** Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="976f0-111">**prompt** es el valor predeterminado cuando se compila una aplicación en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="976f0-111">**prompt** is the default when you compile an application in the development environment.</span></span>

 <span data-ttu-id="976f0-112">**queue**: pone en cola el informe de error.</span><span class="sxs-lookup"><span data-stu-id="976f0-112">**queue** Queues the error report.</span></span> <span data-ttu-id="976f0-113">Cuando inicia sesión con credenciales administrativas, puede notificar los errores que se han producido desde la última vez que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="976f0-113">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="976f0-114">No se le solicitará que envíe informes de error más de una vez cada tres días.</span><span class="sxs-lookup"><span data-stu-id="976f0-114">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="976f0-115">**queue** es el valor predeterminado cuando se compila una aplicación en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="976f0-115">**queue** is the default when you compile an application at the command line.</span></span>

 <span data-ttu-id="976f0-116">**send**: envía automáticamente informes de errores internos del compilador a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="976f0-116">**send** Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="976f0-117">Para habilitar esta opción, debe aceptar la directiva de recopilación de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="976f0-117">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="976f0-118">La primera vez que especifique **-errorreport:send** en un equipo, un mensaje del compilador le remitirá a un sitio web que contiene la directiva de recopilación de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="976f0-118">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>

## <a name="remarks"></a><span data-ttu-id="976f0-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="976f0-119">Remarks</span></span>
 <span data-ttu-id="976f0-120">Cuando el compilador no puede procesar un archivo de código fuente, se produce un error interno del compilador (ICE).</span><span class="sxs-lookup"><span data-stu-id="976f0-120">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="976f0-121">Cuando se produce un ICE, el compilador no genera un archivo de salida ni otro tipo de diagnóstico útil que pueda usar para corregir el código.</span><span class="sxs-lookup"><span data-stu-id="976f0-121">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>

 <span data-ttu-id="976f0-122">En versiones anteriores, cuando recibía un ICE, se le recomendaba que se pusiera en contacto con los servicios de soporte técnico de Microsoft para informar del problema.</span><span class="sxs-lookup"><span data-stu-id="976f0-122">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="976f0-123">Mediante el uso de **-errorreport**, puede proporcionar información sobre los ICE al equipo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="976f0-123">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="976f0-124">Sus informes de error pueden ayudar a mejorar las futuras versiones del compilador.</span><span class="sxs-lookup"><span data-stu-id="976f0-124">Your error reports can help improve future compiler releases.</span></span>

 <span data-ttu-id="976f0-125">La capacidad de un usuario de enviar informes depende de los permisos de directiva de equipo y de usuario.</span><span class="sxs-lookup"><span data-stu-id="976f0-125">A user's ability to send reports depends on computer and user policy permissions.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="976f0-126">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="976f0-126">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="976f0-127">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="976f0-127">Open the project's **Properties** page.</span></span> <span data-ttu-id="976f0-128">Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="976f0-128">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>

2. <span data-ttu-id="976f0-129">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="976f0-129">Click the **Build** property page.</span></span>

3. <span data-ttu-id="976f0-130">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="976f0-130">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="976f0-131">Modifique la propiedad **Informe de errores internos del compilador**.</span><span class="sxs-lookup"><span data-stu-id="976f0-131">Modify the **Internal Compiler Error Reporting** property.</span></span>

 <span data-ttu-id="976f0-132">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="976f0-132">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="976f0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="976f0-133">See also</span></span>

- [<span data-ttu-id="976f0-134">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="976f0-134">C# Compiler Options</span></span>](./index.md)

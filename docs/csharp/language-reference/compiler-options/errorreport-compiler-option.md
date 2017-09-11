---
title: -errorreport (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /errorreport
dev_langs:
- CSharp
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d32ec08da36509527b153166ae15019f129aad71
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="errorreport-c-compiler-options"></a><span data-ttu-id="b5507-102">/errorreport (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b5507-102">/errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="b5507-103">Esta opción proporciona una forma cómoda de notificar un error interno del compilador de C# a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5507-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5507-104">En Windows Vista y Windows Server 2008, la configuración de informes de errores para Visual Studio no reemplaza la configuración realizada a través de Informe de errores de Windows (WER).</span><span class="sxs-lookup"><span data-stu-id="b5507-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="b5507-105">La configuración de WER siempre tiene prioridad sobre la configuración de informes de errores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b5507-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5507-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5507-106">Syntax</span></span>  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="b5507-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b5507-107">Arguments</span></span>  
 <span data-ttu-id="b5507-108">**none**</span><span class="sxs-lookup"><span data-stu-id="b5507-108">**none**</span></span>  
 <span data-ttu-id="b5507-109">No se recopilarán informes sobre errores internos del compilador ni se enviarán a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5507-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="b5507-110">**prompt**</span><span class="sxs-lookup"><span data-stu-id="b5507-110">**prompt**</span></span>  
 <span data-ttu-id="b5507-111">Pregunta si desea enviar un informe cuando recibe un error interno del compilador.</span><span class="sxs-lookup"><span data-stu-id="b5507-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="b5507-112">**prompt** es el valor predeterminado cuando se compila una aplicación en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b5507-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="b5507-113">**queue**</span><span class="sxs-lookup"><span data-stu-id="b5507-113">**queue**</span></span>  
 <span data-ttu-id="b5507-114">Pone en cola el informe de error.</span><span class="sxs-lookup"><span data-stu-id="b5507-114">Queues the error report.</span></span> <span data-ttu-id="b5507-115">Cuando inicia sesión con credenciales administrativas, puede notificar los errores que se han producido desde la última vez que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="b5507-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="b5507-116">No se le solicitará que envíe informes de error más de una vez cada tres días.</span><span class="sxs-lookup"><span data-stu-id="b5507-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="b5507-117">**queue** es el valor predeterminado cuando se compila una aplicación en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b5507-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="b5507-118">**send**</span><span class="sxs-lookup"><span data-stu-id="b5507-118">**send**</span></span>  
 <span data-ttu-id="b5507-119">Envía automáticamente informes de errores internos del compilador a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5507-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="b5507-120">Para habilitar esta opción, debe aceptar la directiva de recopilación de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5507-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="b5507-121">La primera vez que especifique **/errorreport:send** en un equipo, un mensaje del compilador le remitirá a un sitio web que contiene la directiva de recopilación de datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5507-121">The first time that you specify **/errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
  
 <span data-ttu-id="b5507-122">Esta opción depende de la configuración del Registro.</span><span class="sxs-lookup"><span data-stu-id="b5507-122">This option depends on registry settings.</span></span> <span data-ttu-id="b5507-123">Para obtener información sobre cómo establecer los valores apropiados en el Registro, vea las instrucciones sobre [cómo activar la creación automática de informes de errores en las herramientas de línea de comandos de Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695) en el sitio web de MSDN.</span><span class="sxs-lookup"><span data-stu-id="b5507-123">For information about how to set the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695) on the MSDN Web site.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5507-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5507-124">Remarks</span></span>  
 <span data-ttu-id="b5507-125">Cuando el compilador no puede procesar un archivo de código fuente, se produce un error interno del compilador (ICE).</span><span class="sxs-lookup"><span data-stu-id="b5507-125">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="b5507-126">Cuando se produce un ICE, el compilador no genera un archivo de salida ni otro tipo de diagnóstico útil que pueda usar para corregir el código.</span><span class="sxs-lookup"><span data-stu-id="b5507-126">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="b5507-127">En versiones anteriores, cuando recibía un ICE, se le recomendaba que se pusiera en contacto con los servicios de soporte técnico de Microsoft para informar del problema.</span><span class="sxs-lookup"><span data-stu-id="b5507-127">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="b5507-128">Mediante el uso de **/errorreport**, puede proporcionar información sobre los ICE al equipo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b5507-128">By using **/errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="b5507-129">Sus informes de error pueden ayudar a mejorar las futuras versiones del compilador.</span><span class="sxs-lookup"><span data-stu-id="b5507-129">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="b5507-130">La capacidad de un usuario de enviar informes depende de los permisos de directiva de equipo y de usuario.</span><span class="sxs-lookup"><span data-stu-id="b5507-130">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="b5507-131">Para obtener más información sobre el depurador de errores, vea [Descripción de la herramienta Dr. Watson para Windows (Drwtsn32.exe)](http://go.microsoft.com/fwlink/?LinkId=147286).</span><span class="sxs-lookup"><span data-stu-id="b5507-131">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b5507-132">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b5507-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="b5507-133">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5507-133">Open the project's **Properties** page.</span></span> <span data-ttu-id="b5507-134">Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="b5507-134">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="b5507-135">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="b5507-135">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="b5507-136">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="b5507-136">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="b5507-137">Modifique la propiedad **Informe de errores internos del compilador**.</span><span class="sxs-lookup"><span data-stu-id="b5507-137">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="b5507-138">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5507-138">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5507-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5507-139">See Also</span></span>  
 [<span data-ttu-id="b5507-140">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="b5507-140">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)


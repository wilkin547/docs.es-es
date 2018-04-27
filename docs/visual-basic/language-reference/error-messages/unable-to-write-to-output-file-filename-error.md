---
title: 'No se puede escribir en el archivo de salida &#39; &lt;filename&gt;&#39;: &lt;error&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a183f81a73c3c8034d9ba7366be8b36d425263da
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a><span data-ttu-id="03c45-102">No se puede escribir en el archivo de salida &#39; &lt;filename&gt;&#39;: &lt;error&gt;</span><span class="sxs-lookup"><span data-stu-id="03c45-102">Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;</span></span>
<span data-ttu-id="03c45-103">Se ha producido un problema al crear el archivo.</span><span class="sxs-lookup"><span data-stu-id="03c45-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="03c45-104">No se puede abrir un archivo de salida para escritura.</span><span class="sxs-lookup"><span data-stu-id="03c45-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="03c45-105">Puede que otro proceso haya abierto el archivo (o la carpeta que lo contiene) o puede que este tenga establecido el atributo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="03c45-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="03c45-106">A continuación indicamos las situaciones más habituales en la que un archivo se abre de forma exclusiva:</span><span class="sxs-lookup"><span data-stu-id="03c45-106">Common situations where a file is opened exclusively are:</span></span>  
  
-   <span data-ttu-id="03c45-107">La aplicación ya se está ejecutando y usando sus archivos.</span><span class="sxs-lookup"><span data-stu-id="03c45-107">The application is already running and using its files.</span></span> <span data-ttu-id="03c45-108">Para solucionar este problema, asegúrese de que la aplicación no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="03c45-108">To solve this problem, make sure that the application is not running.</span></span>  
  
-   <span data-ttu-id="03c45-109">Otra aplicación ha abierto el archivo.</span><span class="sxs-lookup"><span data-stu-id="03c45-109">Another application has opened the file.</span></span> <span data-ttu-id="03c45-110">Para solucionar este problema, asegúrese de que ninguna otra aplicación está accediendo a los archivos.</span><span class="sxs-lookup"><span data-stu-id="03c45-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="03c45-111">No siempre queda del todo claro qué aplicación está accediendo a los archivos; en tal caso, reiniciar el equipo constituye la forma más sencilla de finalizar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03c45-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="03c45-112">Esta excepción se generará aun cuando solo haya un archivo de salida del proyecto marcado como de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="03c45-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="03c45-113">**Id. de error:** BC31019</span><span class="sxs-lookup"><span data-stu-id="03c45-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03c45-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="03c45-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="03c45-115">Vuelva a compilar el programa para ver si el error se repite.</span><span class="sxs-lookup"><span data-stu-id="03c45-115">Compile the program again to see if the error recurs.</span></span>  
  
2.  <span data-ttu-id="03c45-116">Si el error continúa, guarde el trabajo y reinicie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03c45-116">If the error continues, save your work and restart [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
3.  <span data-ttu-id="03c45-117">Si el error continúa, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="03c45-117">If the error continues, restart the computer.</span></span>  
  
4.  <span data-ttu-id="03c45-118">Si el error persiste, vuelva a instalar Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="03c45-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5.  <span data-ttu-id="03c45-119">Si el error persiste después de la reinstalación, informe al respecto a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03c45-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="03c45-120">Para consultar los atributos de archivo en el Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="03c45-120">To check file attributes in File Explorer</span></span>  
  
1.  <span data-ttu-id="03c45-121">Abra la carpeta que le interese.</span><span class="sxs-lookup"><span data-stu-id="03c45-121">Open the folder you are interested in.</span></span>  
  
2.  <span data-ttu-id="03c45-122">Haga clic en el **vistas** icono y elija **detalles**.</span><span class="sxs-lookup"><span data-stu-id="03c45-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3.  <span data-ttu-id="03c45-123">Haga clic en el encabezado de columna y elija **atributos** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="03c45-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="03c45-124">Para cambiar los atributos de un archivo o carpeta</span><span class="sxs-lookup"><span data-stu-id="03c45-124">To change the attributes of a file or folder</span></span>  
  
1.  <span data-ttu-id="03c45-125">En **Explorador de archivos**, haga clic en el archivo o carpeta y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="03c45-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="03c45-126">En el **atributos** sección de la **General** ficha, desactive la **de sólo lectura** cuadro.</span><span class="sxs-lookup"><span data-stu-id="03c45-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3.  <span data-ttu-id="03c45-127">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="03c45-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c45-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="03c45-128">See Also</span></span>  
 [<span data-ttu-id="03c45-129">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="03c45-129">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

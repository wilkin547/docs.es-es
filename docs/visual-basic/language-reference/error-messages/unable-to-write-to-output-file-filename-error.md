---
description: "Más información acerca de: BC31019: no se puede escribir en el archivo de salida ' <filename> ': <error>"
title: "No se puede escribir en el archivo de resultados '<filename>': <error>"
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: 86ddd01764d51c3050186e99e047edb8aba158eb
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104813"
---
# <a name="bc31019-unable-to-write-to-output-file-filename-error"></a><span data-ttu-id="7e0aa-103">BC31019: no se puede escribir en el archivo de salida ' \<filename> ': \<error></span><span class="sxs-lookup"><span data-stu-id="7e0aa-103">BC31019: Unable to write to output file '\<filename>': \<error></span></span>

<span data-ttu-id="7e0aa-104">Se ha producido un problema al crear el archivo.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-104">There was a problem creating the file.</span></span>

 <span data-ttu-id="7e0aa-105">No se puede abrir un archivo de salida para escritura.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-105">An output file cannot be opened for writing.</span></span> <span data-ttu-id="7e0aa-106">Puede que otro proceso haya abierto el archivo (o la carpeta que lo contiene) o puede que este tenga establecido el atributo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-106">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>

 <span data-ttu-id="7e0aa-107">A continuación indicamos las situaciones más habituales en la que un archivo se abre de forma exclusiva:</span><span class="sxs-lookup"><span data-stu-id="7e0aa-107">Common situations where a file is opened exclusively are:</span></span>

- <span data-ttu-id="7e0aa-108">La aplicación ya se está ejecutando y usando sus archivos.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-108">The application is already running and using its files.</span></span> <span data-ttu-id="7e0aa-109">Para solucionar este problema, asegúrese de que la aplicación no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-109">To solve this problem, make sure that the application is not running.</span></span>

- <span data-ttu-id="7e0aa-110">Otra aplicación ha abierto el archivo.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-110">Another application has opened the file.</span></span> <span data-ttu-id="7e0aa-111">Para solucionar este problema, asegúrese de que ninguna otra aplicación está accediendo a los archivos.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-111">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="7e0aa-112">No siempre queda del todo claro qué aplicación está accediendo a los archivos; en tal caso, reiniciar el equipo constituye la forma más sencilla de finalizar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-112">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>

 <span data-ttu-id="7e0aa-113">Esta excepción se generará aun cuando solo haya un archivo de salida del proyecto marcado como de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-113">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>

 <span data-ttu-id="7e0aa-114">**Identificador de error:** BC31019</span><span class="sxs-lookup"><span data-stu-id="7e0aa-114">**Error ID:** BC31019</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7e0aa-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7e0aa-115">To correct this error</span></span>

1. <span data-ttu-id="7e0aa-116">Vuelva a compilar el programa para ver si el error se repite.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-116">Compile the program again to see if the error recurs.</span></span>

2. <span data-ttu-id="7e0aa-117">Si el error continúa, guarde el trabajo y reinicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-117">If the error continues, save your work and restart Visual Studio.</span></span>

3. <span data-ttu-id="7e0aa-118">Si el error continúa, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-118">If the error continues, restart the computer.</span></span>

4. <span data-ttu-id="7e0aa-119">Si el error se repite, reinstale Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-119">If the error recurs, reinstall Visual Basic.</span></span>

5. <span data-ttu-id="7e0aa-120">Si el error persiste después de la reinstalación, informe al respecto a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-120">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>

### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="7e0aa-121">Para consultar los atributos de archivo en el Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="7e0aa-121">To check file attributes in File Explorer</span></span>

1. <span data-ttu-id="7e0aa-122">Abra la carpeta que le interese.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-122">Open the folder you are interested in.</span></span>

2. <span data-ttu-id="7e0aa-123">Haga clic en el icono **vistas** y elija **detalles**.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-123">Click the **Views** icon and choose **Details**.</span></span>

3. <span data-ttu-id="7e0aa-124">Haga clic con el botón secundario en el encabezado de columna y elija **atributos** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-124">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>

### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="7e0aa-125">Para cambiar los atributos de un archivo o carpeta</span><span class="sxs-lookup"><span data-stu-id="7e0aa-125">To change the attributes of a file or folder</span></span>

1. <span data-ttu-id="7e0aa-126">En el **Explorador de archivos**, haga clic con el botón derecho en el archivo o la carpeta y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-126">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>

2. <span data-ttu-id="7e0aa-127">En la sección **atributos** de la ficha **General** , desactive la casilla **solo lectura** .</span><span class="sxs-lookup"><span data-stu-id="7e0aa-127">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>

3. <span data-ttu-id="7e0aa-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e0aa-128">Press **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e0aa-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e0aa-129">See also</span></span>

- [<span data-ttu-id="7e0aa-130">Opciones de comentarios de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7e0aa-130">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)

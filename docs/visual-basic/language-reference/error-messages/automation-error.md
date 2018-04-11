---
title: Error de automatización
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a><span data-ttu-id="ab6af-102">Error de automatización</span><span class="sxs-lookup"><span data-stu-id="ab6af-102">Automation error</span></span>
<span data-ttu-id="ab6af-103">Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="ab6af-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="ab6af-104">El error se notificó a través de la aplicación que creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="ab6af-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ab6af-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ab6af-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="ab6af-106">Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="ab6af-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="ab6af-107">Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.</span><span class="sxs-lookup"><span data-stu-id="ab6af-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab6af-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab6af-108">See Also</span></span>  
 [<span data-ttu-id="ab6af-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="ab6af-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="ab6af-110">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="ab6af-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

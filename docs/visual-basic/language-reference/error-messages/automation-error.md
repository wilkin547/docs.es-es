---
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e0ebaabb14cf5685469f88b0be3b7fece017165e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843661"
---
# <a name="automation-error"></a><span data-ttu-id="8cdf9-102">Error de automatización</span><span class="sxs-lookup"><span data-stu-id="8cdf9-102">Automation error</span></span>
<span data-ttu-id="8cdf9-103">Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="8cdf9-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="8cdf9-104">El error se notificó a través de la aplicación que creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="8cdf9-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8cdf9-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8cdf9-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="8cdf9-106">Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="8cdf9-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="8cdf9-107">Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.</span><span class="sxs-lookup"><span data-stu-id="8cdf9-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdf9-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cdf9-108">See also</span></span>

- [<span data-ttu-id="8cdf9-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="8cdf9-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="8cdf9-110">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="8cdf9-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

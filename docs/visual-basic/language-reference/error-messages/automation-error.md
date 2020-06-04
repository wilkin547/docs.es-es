---
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: d62ba57db8bffefb2cfebed705251d87fe285602
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409899"
---
# <a name="automation-error"></a><span data-ttu-id="a455d-102">Error de automatización</span><span class="sxs-lookup"><span data-stu-id="a455d-102">Automation error</span></span>

<span data-ttu-id="a455d-103">Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="a455d-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="a455d-104">El error se notificó a través de la aplicación que creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="a455d-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a455d-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a455d-105">To correct this error</span></span>  
  
1. <span data-ttu-id="a455d-106">Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="a455d-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="a455d-107">Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.</span><span class="sxs-lookup"><span data-stu-id="a455d-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a455d-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a455d-108">See also</span></span>

- [<span data-ttu-id="a455d-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="a455d-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="a455d-110">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="a455d-110">Talk to Us</span></span>](/visualstudio/ide/feedback-options)

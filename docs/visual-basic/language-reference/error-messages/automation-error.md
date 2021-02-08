---
description: 'Más información acerca de: error de Automation'
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e4d283b16b4c54e2488fedfc58d3c881cf6b0218
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797125"
---
# <a name="automation-error"></a><span data-ttu-id="ec781-103">Error de automatización</span><span class="sxs-lookup"><span data-stu-id="ec781-103">Automation error</span></span>

<span data-ttu-id="ec781-104">Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="ec781-104">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="ec781-105">El error se notificó a través de la aplicación que creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="ec781-105">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ec781-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ec781-106">To correct this error</span></span>  
  
1. <span data-ttu-id="ec781-107">Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="ec781-107">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="ec781-108">Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.</span><span class="sxs-lookup"><span data-stu-id="ec781-108">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec781-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec781-109">See also</span></span>

- [<span data-ttu-id="ec781-110">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="ec781-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="ec781-111">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="ec781-111">Talk to Us</span></span>](/visualstudio/ide/feedback-options)

---
description: 'Más información acerca de: error de Automation'
title: Error de automatización
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: bf3e61bb9b8fec9a831d211b70abdca322c1fe06
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106610"
---
# <a name="automation-error"></a><span data-ttu-id="fe6f6-103">Error de automatización</span><span class="sxs-lookup"><span data-stu-id="fe6f6-103">Automation error</span></span>

<span data-ttu-id="fe6f6-104">Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-104">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="fe6f6-105">El error se notificó a través de la aplicación que creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-105">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fe6f6-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="fe6f6-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fe6f6-107">Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-107">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="fe6f6-108">Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-108">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6f6-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe6f6-109">See also</span></span>

- [<span data-ttu-id="fe6f6-110">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="fe6f6-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="fe6f6-111">Opciones de comentarios de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fe6f6-111">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)

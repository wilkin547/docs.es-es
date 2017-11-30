---
title: Proteger los datos de estado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd41f5174f426e723ea7e069eaee8f2d367625a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="securing-state-data"></a><span data-ttu-id="6768a-102">Proteger los datos de estado</span><span class="sxs-lookup"><span data-stu-id="6768a-102">Securing State Data</span></span>
<span data-ttu-id="6768a-103">Las aplicaciones que administran datos confidenciales o realizan cualquier tipo de decisiones de seguridad necesitan mantener los datos bajo control y no pueden permitir que otro código potencialmente malintencionado acceda directamente a los datos.</span><span class="sxs-lookup"><span data-stu-id="6768a-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="6768a-104">La mejor manera de proteger los datos en memoria es declarar los datos como variables privadas o internas (con el ámbito limitado al mismo ensamblado).</span><span class="sxs-lookup"><span data-stu-id="6768a-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="6768a-105">Sin embargo, incluso estos datos están sujetos a acceso, por lo que debe tenerse en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6768a-105">However, even this data is subject to access you should be aware of:</span></span>  
  
-   <span data-ttu-id="6768a-106">Al usar mecanismos de reflexión, se puede obtener y establecer miembros privados en el código de plena confianza al que puede hacer referencia el objeto.</span><span class="sxs-lookup"><span data-stu-id="6768a-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
-   <span data-ttu-id="6768a-107">Con la serialización, el código de plena confianza puede obtener y establecer eficazmente miembros privados si pueden acceder a los datos correspondientes en el formulario serializado del objeto.</span><span class="sxs-lookup"><span data-stu-id="6768a-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
-   <span data-ttu-id="6768a-108">En la depuración, se pueden leer estos datos.</span><span class="sxs-lookup"><span data-stu-id="6768a-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="6768a-109">Asegúrese de que ninguno de sus métodos o propiedades expone estos valores de manera involuntaria.</span><span class="sxs-lookup"><span data-stu-id="6768a-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6768a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6768a-110">See Also</span></span>  
 [<span data-ttu-id="6768a-111">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="6768a-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)

---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 9235f1bcda7529b71aef542d3a49da08a9d4b59e
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592127"
---
<span data-ttu-id="9a64b-101">Los deserializadores inseguros son vulnerables al deserializar datos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="9a64b-101">Insecure deserializers are vulnerable when deserializing untrusted data.</span></span> <span data-ttu-id="9a64b-102">Un atacante podría modificar los datos serializados para incluir tipos inesperados para insertar objetos con efectos secundarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="9a64b-102">An attacker could modify the serialized data to include unexpected types to inject objects with malicious side effects.</span></span> <span data-ttu-id="9a64b-103">Un ataque contra un deserializador inseguro podría, por ejemplo, ejecutar comandos en el sistema operativo subyacente, comunicarse a través de la red o eliminar archivos.</span><span class="sxs-lookup"><span data-stu-id="9a64b-103">An attack against an insecure deserializer could, for example, execute commands on the underlying operating system, communicate over the network, or delete files.</span></span>

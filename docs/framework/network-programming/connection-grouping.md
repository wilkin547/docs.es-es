---
title: Agrupación de conexiones
ms.date: 03/30/2017
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
ms.openlocfilehash: 8bd4412a4c13dd490fce3118f59b5bb1f0d3ea85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250572"
---
# <a name="connection-grouping"></a><span data-ttu-id="95d46-102">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="95d46-102">Connection Grouping</span></span>

<span data-ttu-id="95d46-103">La agrupación de conexiones asocia solicitudes específicas de una aplicación individual a un grupo de conexiones definido.</span><span class="sxs-lookup"><span data-stu-id="95d46-103">Connection grouping associates specific requests within a single application to a defined connection pool.</span></span> <span data-ttu-id="95d46-104">Esto puede ser exigido por una aplicación de nivel intermedio que se conecta a un servidor back-end en nombre de un usuario y usa un protocolo de autenticación que admite la delegación, como Kerberos, o por una aplicación de nivel medio que proporciona sus propias credenciales, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="95d46-104">This can be required by a middle-tier application that connects to a back-end server on behalf of a user and uses an authentication protocol that supports delegation, such as Kerberos, or by a middle-tier application that supplies its own credentials, as in the example below.</span></span> <span data-ttu-id="95d46-105">Por ejemplo, imagine que un usuario, Juan, visita un sitio web interno que muestra información de su nómina.</span><span class="sxs-lookup"><span data-stu-id="95d46-105">For example, suppose a user, Joe, visits an internal Web site that displays his payroll information.</span></span> <span data-ttu-id="95d46-106">Después de autenticar a Juan, el servidor de aplicación de nivel intermedio usa las credenciales de Juan para conectarse al servidor back-end a fin de recuperar la información de su nómina.</span><span class="sxs-lookup"><span data-stu-id="95d46-106">After authenticating Joe, the middle-tier application server uses Joe's credentials to connect to the back-end server to retrieve his payroll information.</span></span> <span data-ttu-id="95d46-107">Luego Susana visita el sitio y solicita información de su nómina.</span><span class="sxs-lookup"><span data-stu-id="95d46-107">Next, Susan visits the site and requests her payroll information.</span></span> <span data-ttu-id="95d46-108">Dado que la aplicación de nivel intermedio ya ha realizado una conexión con las credenciales de Juan, el servidor back-end responde con la información de Juan.</span><span class="sxs-lookup"><span data-stu-id="95d46-108">Because the middle-tier application has already made a connection using Joe's credentials, the back-end server responds with Joe's information.</span></span> <span data-ttu-id="95d46-109">Pero si la aplicación asigna cada solicitud enviada al servidor back-end a un grupo de conexiones formado a partir del nombre de usuario, cada usuario pertenece a un grupo de conexiones independiente y no puede compartir accidentalmente la información de autenticación con otro usuario.</span><span class="sxs-lookup"><span data-stu-id="95d46-109">However, if the application assigns each request sent to the back-end server to a connection group formed from the user name, then each user belongs to a separate connection pool and cannot accidentally share authentication information with another user.</span></span>  
  
 <span data-ttu-id="95d46-110">Para asignar una solicitud a un grupo de conexiones concreto, debe asignar un nombre a la propiedad <xref:System.Net.WebRequest.ConnectionGroupName%2A> de <xref:System.Net.WebRequest> antes de realizar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="95d46-110">To assign a request to a specific connection group, you must assign a name to the <xref:System.Net.WebRequest.ConnectionGroupName%2A> property of your <xref:System.Net.WebRequest> before making the request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d46-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="95d46-111">See also</span></span>

- [<span data-ttu-id="95d46-112">Administración de conexiones</span><span class="sxs-lookup"><span data-stu-id="95d46-112">Managing Connections</span></span>](managing-connections.md)
- [<span data-ttu-id="95d46-113">Cómo: asignar la información de usuario para agrupar conexiones</span><span class="sxs-lookup"><span data-stu-id="95d46-113">How to: Assign User Information to Group Connections</span></span>](how-to-assign-user-information-to-group-connections.md)

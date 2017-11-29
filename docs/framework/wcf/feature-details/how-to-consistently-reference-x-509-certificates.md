---
title: "Cómo: Hacer referencia a los certificados X.509 de forma coherente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d42af919b9792fc5a5303737187be7ffef6405d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Cómo: Hacer referencia a los certificados X.509 de forma coherente
Hay varias maneras de identificar un certificado: por el hash del certificado, por el emisor y número de serie y por el identificador clave del sujeto (SKI). El SKI proporciona una identificación única para la clave pública del sujeto del certificado y se suele utilizar al trabajar con firmas digitales XML. El valor de SKI normalmente es parte del certificado X.509 como una *extensión de certificado X.509*. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]tiene una restricción default *estilo de referencia* que usa el emisor y el número de serie si la extensión SKI no está presente en el certificado. Si el certificado contiene la extensión SKI, el estilo de referencia predeterminado utiliza el SKI para señalar al certificado. Si en la mitad del desarrollo de una aplicación cambia de utilizar certificados que no utilizan la extensión SKI a certificados que utilizan la extensión SKI, el estilo de referencia utilizado en mensajes generados [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]también cambia.  
  
 Si un estilo de referencia coherente se requiere independientemente de la presencia de extensión SKI, es posible configurar el estilo de referencia deseado como se muestra en el código siguiente.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un elemento de enlace de seguridad personalizado que utiliza un estilo de referencia coherente único, el nombre del emisor y número de serie.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los espacios de nombres siguientes son necesarios para compilar el código:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

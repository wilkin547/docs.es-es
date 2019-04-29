---
title: Procedimiento para hacer referencia a los certificados X.509 de forma coherente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: bd911b1586f7f4a4816efa32480ef99ca12404f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699531"
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Procedimiento para hacer referencia a los certificados X.509 de forma coherente
Hay varias maneras de identificar un certificado: por el hash del certificado, por el emisor y número de serie y por el identificador clave del sujeto (SKI). El SKI proporciona una identificación única para la clave pública del sujeto del certificado y se suele utilizar al trabajar con firmas digitales XML. El valor SKI normalmente forma parte del certificado X.509 como una *extensión de certificado X.509*. Windows Communication Foundation (WCF) tiene un valor predeterminado *estilo de referencia* que usa el emisor y número de serie si la extensión SKI falta en el certificado. Si el certificado contiene la extensión SKI, el estilo de referencia predeterminado utiliza el SKI para señalar al certificado. Si la mitad del desarrollo de una aplicación, cambia del uso de certificados que no usan la extensión SKI a certificados que utilizan la extensión SKI, también cambia el estilo de referencia que se usan en los mensajes generados por WCF.  
  
 Si un estilo de referencia coherente se requiere independientemente de la presencia de extensión SKI, es posible configurar el estilo de referencia deseado como se muestra en el código siguiente.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un elemento de enlace de seguridad personalizado que utiliza un estilo de referencia coherente único, el nombre del emisor y número de serie.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los espacios de nombres siguientes son necesarios para compilar el código:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>Vea también

- [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

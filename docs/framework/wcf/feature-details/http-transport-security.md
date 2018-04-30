---
title: Seguridad de transporte HTTP
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3439262-c58e-4d30-9f2b-a160170582bb
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 2787c38603fd0f88878596a809d7e3c5cfdfb350
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="http-transport-security"></a>Seguridad de transporte HTTP
Al utilizar HTTP como transporte, una implementación de Capa de sockets seguros (SSL) proporciona la seguridad. SSL se utiliza mucho en Internet para autenticar un servicio a un cliente y proporcionar la confidencialidad (cifrado) al canal. En este tema se explica cómo funciona SSL y cómo se implementa en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="basic-ssl"></a>SSL Básico  
 El funcionamiento de SSL se explica mejor a través de un escenario típico, en este caso, el sitio web de un banco. El sitio permite que un cliente inicie sesión con un nombre de usuario y contraseña. Después de autenticarse, el usuario puede realizar transacciones, como ver los saldos de la cuenta, pagar facturas y pasar dinero de una cuenta a otra.  
  
 Cuando un usuario visita el sitio por primera vez, el mecanismo de SSL comienza una serie de negociaciones, llamadas un *mutuo*, con el cliente del usuario (en este caso, Internet Explorer). SSL autentica primero el sitio bancario al cliente. Éste es un paso esencial porque los clientes deben conocer primero que están comunicando con el sitio real, y que no es un engaño que intenta hacer que escriban su nombre de usuario y contraseña. SSL hace esta autenticación utilizando un Certificado SSL proporcionado por una autoridad de confianza, como VeriSign. La lógica es así: VeriSign asegura la identidad del sitio bancario. Dado que Internet Explorer confía en VeriSign, se confía en el sitio. Si desea consultar con VeriSign, puede hacerlo haciendo clic en el logotipo de VeriSign. Eso presenta una instrucción de autenticidad con su fecha de caducidad y a quién se emite (el sitio bancario).  
  
 Para iniciar una sesión segura, el cliente envía el equivalente de un "hello" al servidor junto con una lista de algoritmos criptográficos que puede utilizar para firmar, generar los hash y cifrar y descifrar. En respuesta, el sitio devuelve un reconocimiento y su opción de uno de los conjuntos de algoritmos. Durante este protocolo de enlace inicial, ambas partes envían y reciben valores de seguridad (nonces). A *nonce* es un fragmento de datos que se usan en combinación con la clave pública del sitio para crear un hash generado aleatoriamente. A *hash* es un número nuevo que se deriva de los dos números utilizando un algoritmo estándar, como SHA1. (El cliente y el sitio también intercambian mensajes para acordar qué algoritmo hash se debe usar.) El hash es único y se utiliza solo para la sesión entre el cliente y el sitio para cifrar y descifrar los mensajes. El cliente y el servicio tienen el nonce original y la clave pública del certificado, por lo que ambos lados pueden generar el mismo hash. Por consiguiente, el cliente valida el hash enviado por el servicio (a) usando el algoritmo acordado para calcular el hash a partir de los datos y (b) comparándolo con el hash enviado por el servicio; si ambos coinciden, el cliente tiene la convicción de que no se ha manipulado el hash. El cliente puede utilizar a continuación este hash como clave para cifrar un mensaje que todavía contiene otro nuevo hash. El servicio puede descifrar el mensaje mediante el hash y recupera este antepenúltimo hash. La información acumulada (nonces, clave pública y otros datos) se conoce ahora en ambos lados y se puede crear un hash (o clave maestra) final. Esta clave final se envía cifrada mediante el penúltimo hash. La clave maestra se utiliza a continuación para cifrar y descifrar los mensajes para el reinicio de la sesión. Dado que tanto el cliente como el servicio utilizan la misma clave, también se denomina un *clave de sesión*.  
  
 La clave de sesión también se caracteriza por ser una clave simétrica o un "secreto compartido." Tener una clave simétrica es importante, porque reduce el cálculo requerido por ambos lados de la transacción. Si cada mensaje exigiera un nuevo intercambio de nonces y hash, el rendimiento se deterioraría. Por consiguiente, el objetivo último de SSL es utilizar una clave simétrica que permita a los mensajes fluir libremente entre los dos lados con un grado mayor de seguridad y eficacia.  
  
 La descripción anterior es una versión simplificada de lo que ocurre, porque el protocolo puede variar de sitio a sitio. También es posible que el cliente y el sitio generen nonces que se combinan de manera algorítmica durante el protocolo de enlace para agregar más complejidad y, por consiguiente, protección, al proceso de intercambio de datos.  
  
### <a name="certificates-and-public-key-infrastructure"></a>Certificados e infraestructura de clave pública (PKI)  
 Durante el protocolo de enlace, el servicio envía también su Certificado SSL al cliente. El certificado contiene información, como su fecha de caducidad, autoridad emisora y el Identificador uniforme de recursos del sitio (URI). El cliente compara el URI con el URI que había contactado originalmente para asegurarse una coincidencia y comprueba, también, la fecha y autoridad emisora.  
  
 Cada certificado tiene dos claves, una clave privada y una clave pública y los dos se conocen como un *par de claves de exchange*. En resumen, la clave privada solo es conocida por el propietario del certificado mientras que la clave pública es legible por el certificado. La clave se puede utilizar para cifrar o descifrar un resumen, hash u otra clave, pero solo como operaciones contrarias. Por ejemplo, si el cliente cifra con clave pública, solo el sitio puede descifrar el mensaje mediante la clave privada. De igual forma, si el sitio cifra la clave privada, el cliente puede descifrar con la clave pública. Esto proporciona garantía al cliente de que los mensajes solo se intercambian con el poseedor de la clave privada, porque solo los mensajes cifrados con la clave privada se pueden descifrar con la clave pública. Se garantiza que el sitio está intercambiando los mensajes con un cliente que se ha cifrado utilizando la clave pública. Este intercambio solo es seguro para un protocolo de enlace inicial, motivo por el cual se hace mucho más para crear la clave simétrica real. No obstante, todas las comunicaciones dependen del servicio que tiene un certificado SSL válido.  
  
## <a name="implementing-ssl-with-wcf"></a>Implementar SSL con WCF  
 La seguridad del transporte HTTP (o SSL) se proporciona externamente a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Puede implementar SSL de dos maneras; el factor decisivo es cómo se hospeda su aplicación:  
  
-   Si está utilizando Internet Information Services (IIS) como su host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilice la infraestructura de IIS para configurar un servicio de SSL.  
  
-   Si está creando una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autohospedada, puede enlazar un certificado SSL a la dirección utilizando la herramienta HttpCfg.exe.  
  
### <a name="using-iis-for-transport-security"></a>Utilizar IIS para seguridad de transporte   
  
#### <a name="iis-70"></a>IIS 7.0  
 Para configurar [!INCLUDE[iisver](../../../../includes/iisver-md.md)] como un host seguro (mediante SSL), consulte [IIS 7.0 Beta: configurar la capa de Sockets seguros en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88600).  
  
 Para configurar certificados para su uso con [!INCLUDE[iisver](../../../../includes/iisver-md.md)], consulte [IIS 7.0 Beta: configurar certificados de servidor en IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=88595).  
  
#### <a name="iis-60"></a>IIS 6,0  
 Para configurar [!INCLUDE[iis601](../../../../includes/iis601-md.md)] como un host seguro (mediante SSL), consulte [configurar la capa de Sockets seguros](http://go.microsoft.com/fwlink/?LinkId=88601).  
  
 Para configurar certificados para su uso con [!INCLUDE[iis601](../../../../includes/iis601-md.md)], consulte [Certificates_IIS_SP1_Ops](http://go.microsoft.com/fwlink/?LinkId=88602).  
  
### <a name="using-httpcfg-for-ssl"></a>Utilizar HttpCfg para SSL  
 Si está creando un autohospedado [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplicación, descargue la herramienta HttpCfg.exe, disponible en la [sitio de herramientas de soporte técnico de Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?LinkId=29002).  
  
 Para obtener más información sobre cómo usar la herramienta HttpCfg.exe para configurar un puerto con un certificado X.509, consulte [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Seguridad de los mensajes](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)

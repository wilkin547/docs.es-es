---
title: "Direccionamiento IPv6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Protocolo de Internet, versión 6, direcciones"
  - "Detección de equipos cercanos"
  - "IPv6, habilitar"
  - "IPv6, movilidad y"
  - "Protocolo de Internet versión 6, direcciones de difusión por proximidad"
  - "IPv6, detección de equipos cercanos"
  - "Protocolo de Internet versión 6, configuración automática"
  - "Protocolo de Internet versión 6, habilitar"
  - "IPv6, direcciones de unidifusión"
  - "IPv6, configuración automática"
  - "Protocolo de Internet versión 6, enrutamiento"
  - "IPv6, documentos RFC"
  - "IPv6, enrutamiento"
  - "Protocolo de Internet versión 6, deshabilitar"
  - "Protocolo de Internet versión 6, direcciones de unidifusión"
  - "IPv6, direcciones de multidifusión"
  - "Protocolo de Internet versión 6, movilidad y"
  - "Protocolo de Internet versión 6, documentos RFC"
  - "Protocolo de Internet versión 6, detección de equipos cercanos"
  - "IPv6, direcciones de difusión por proximidad"
  - "Protocolo de Internet versión 6, direcciones de multidifusión"
  - "IPv6, direcciones"
  - "IPv6, deshabilitar"
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Direccionamiento IPv6
En el protocolo de Internet versión 6 \(IPv6\), las direcciones de 128 bits.  Una razón de un espacio de direcciones tan grande es subdividir direcciones disponible en una jerarquía de dominios de enrutamiento que reflejan la topología de Internet.  Otra razón es asignar las direcciones de los adaptadores de red \(o de las interfaces\) que conectan los dispositivos de red.  IPv6 representa una capacidad inherente de resolver direcciones en el nivel más bajo, que está en el nivel de interfaz de red, y también tiene capacidades de configuración automática.  
  
## Representación de texto  
 Los siguientes son las tres formas convencionales utilizados para representar las direcciones de IPv6 como cadenas de texto:  
  
-   **Colon\-hexadecimal form**.  Ésta es la n preferida del formulario: n: n: n: n: n: n: n.  Cada n representa el valor hexadecimal de uno de los ocho elementos de 16 bits de dirección.  Por ejemplo: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.  
  
-   **Compressed form**.  Debido a la longitud de la dirección, suelen tener direcciones que contienen una cadena larga de ceros.  Para simplificar la escritura de estas direcciones, utilice el formato comprimido, en el que una sola secuencia contigua de 0 bloques se representa mediante un símbolo de doble\- dos puntos \(::\).  Este símbolo sólo puede aparecer una vez en una dirección.  Por ejemplo, la dirección de multidifusión `FFED:0:0:0:0:BA98:3210:4562` en formato comprimido es `FFED::BA98:3210:4562`.  La dirección de unidifusión `3FFE:FFFF:0:0:8:800:20C4:0` en formato comprimido es `3FFE:FFFF::8:800:20C4:0`.  La dirección de bucle invertido `0:0:0:0:0:0:0:1` en formato comprimido es `::`1.  La dirección sin especificar `0:0:0:0:0:0:0:0` en formato comprimido es `::`.  
  
-   **Mixed form**.  Este formulario combina direcciones de IPv4 e IPv6.  En este caso, el formato de dirección es n: n: n: n: n: n: d.d.d.d, donde cada n representa los valores hexadecimales de los seis elementos de 16 bits de alto nivel de dirección de IPv6, y cada d representa el valor decimal de una dirección IPv4.  
  
## Tipos de dirección  
 Los bits principales en la dirección definen el tipo específico de la dirección IPv6.  El campo de longitud variable que contiene estos bits principales se denomina un prefijo \(FP\) de formato.  
  
 Dividen una dirección de unidifusión de IPv6 en dos partes.  La primera parte contiene el prefijo de dirección, y la segunda parte contiene el identificador de interfaz.  Una manera concisa de expresar una dirección IPv6 o una combinación de prefijo es la siguiente: ipv6\-address\/longitud de prefijo.  
  
 A continuación se muestra un ejemplo de una dirección con un prefijo de 64 bits.  
  
 `3FFE:FFFF:0:CD30:0:0:0:0/64`.  
  
 El prefijo en este ejemplo es `3FFE:FFFF:0:CD30`.  La dirección también se puede escribir en un formato comprimido, como `3FFE:FFFF:0:CD30::/64`.  
  
 IPv6 define los siguientes tipos de dirección:  
  
-   **Unicast address**.  Un identificador para una única interfaz.  Un paquete enviado esta dirección se entrega a la interfaz identificada.  Las direcciones de unidifusión se diferencian de las direcciones de multidifusión para el valor de octeto de alto nivel.  El octeto de alto nivel de las direcciones de multidifusión tiene el valor hexadecimal de avance de página.  Cualquier otro valor para este octeto identifica una dirección de unidifusión.  Los siguientes son diferentes tipos de direcciones de unidifusión:  
  
    -   **Link\-local addresses**.  Utilizan en un único vínculo y tienen a estas direcciones el formato siguiente: FE80::*InterfaceID*.  Utilizan direcciones locales de los vínculos entre los nodos en un vínculo para la configuración de la auto\- dirección, detección de vecinos, o cuando no hay enrutadores presentes.  Utilizan una dirección local de vínculo principalmente al inicio y cuando el sistema aún no ha adquirido direcciones de ámbito mayor.  
  
    -   **Site\-local addresses**.  Utilizan en un único sitio y tienen a estas direcciones el formato siguiente: FEC0::*SubnetID*:*InterfaceID*.  Utilizan direcciones locales del sitio para dirigir dentro de un sitio sin necesidad de un prefijo global.  
  
    -   **Global IPv6 unicast addresses**.  Estas direcciones se pueden utilizar a través de Internet y tener el formato siguiente: 010 \(punto de congelación, 3 bits\) id. de TLA \(13 bits\) reservaron \(8 bits\) el id. de id. de NLA \(24 bits\) SLA \(16 bits\) *InterfaceID* \(64 bits\).  
  
-   **Multicast address**.  Un identificador para un conjunto de interfaces \(que pertenecen normalmente a diversos nodos\).  Un paquete enviado esta dirección se entrega a todas las interfaces identificadas por la dirección.  Los tipos de la dirección de multidifusión reemplazan a las direcciones de difusión IPv4.  
  
-   **Anycast address**.  Un identificador para un conjunto de interfaces \(que pertenecen normalmente a diversos nodos\).  Un paquete enviado esta dirección se entrega a una única interfaz identificada por la dirección.  Ésta es la interfaz más próxima según se identifica mediante métricas.  Toman de espacio de dirección de unidifusión y no son sintácticamente distinguibles las direcciones de difusión por proximidad.  La interfaz dirigida realiza la distinción entre la unidifusión y direcciones de difusión por proximidad en función de la configuración.  
  
 Un nodo suele siempre una dirección local del vínculo.  Puede tener una dirección local del sitio y una o más direcciones globales.  
  
## Vea también  
 [Protocolo de Internet versión 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)
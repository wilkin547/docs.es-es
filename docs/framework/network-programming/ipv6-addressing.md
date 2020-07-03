---
title: Direccionamiento IPv6
description: Obtenga información sobre la versión 6 del protocolo de Internet (IPv6), las direcciones, la representación de texto y los tipos de dirección.
ms.date: 03/30/2017
helpviewer_keywords:
- Internet Protocol version 6, addresses in
- Neighbor Discovery
- IPv6, enabling
- IPv6, mobility and
- Internet Protocol version 6, anycast addresses
- IPv6, Neighbor Discovery
- Internet Protocol version 6, auto-configuring
- Internet Protocol version 6, enabling
- IPv6, unicast addresses
- IPv6, auto-configuring
- Internet Protocol version 6, routing
- IPv6, RFC documents
- IPv6, routing
- Internet Protocol version 6, disabling
- Internet Protocol version 6, unicast addresses
- IPv6, multicast addresses
- Internet Protocol version 6, mobility and
- Internet Protocol version 6, RFC documents
- Internet Protocol version 6, Neighbor Discovery
- IPv6, anycast addresses
- Internet Protocol version 6, multicast addresses
- IPv6, addresses in
- IPv6, disabling
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
ms.openlocfilehash: fbf68cb5f40450c2f9ecf4900801ee55e326fcb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502345"
---
# <a name="ipv6-addressing"></a>Direccionamiento IPv6

En el protocolo de Internet versión 6 (IPv6), las direcciones tienen una longitud de 128 bits. Entre otras razones, el espacio de direcciones es tan grande para subdividir las direcciones disponibles en una jerarquía de dominios de enrutamiento que reflejen la topología de Internet y para asignar las direcciones de los adaptadores de red (o interfaces) que conectan los dispositivos a la red. IPv6 se caracteriza por una capacidad inherente para resolver direcciones en su nivel más bajo, que es el nivel de la interfaz de red, y cuenta con funciones de configuración automática.

## <a name="text-representation"></a>Representación de texto

A continuación se indican los tres formatos convencionales que se usan para representar las direcciones IPv6 como cadenas de texto:

- **Formato hexadecimal con dos puntos**. Se trata de la forma preferida: n:n:n:n:n:n:n:n. Cada n representa el valor hexadecimal de uno de los ocho elementos de 16 bits de la dirección. Por ejemplo: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.

- **Formato comprimido**. Debido a la longitud de la dirección, es habitual tener direcciones con una larga cadena de ceros. Para simplificar la escritura de estas direcciones, use el formato comprimido, en el que una secuencia contigua de bloques de 0 se representa mediante un símbolo de dos puntos dobles (::). Este símbolo solo puede aparecer una vez en una dirección. Por ejemplo, la dirección de multidifusión `FFED:0:0:0:0:BA98:3210:4562` en formato comprimido es `FFED::BA98:3210:4562`. La dirección de unidifusión `3FFE:FFFF:0:0:8:800:20C4:0` en formato comprimido es `3FFE:FFFF::8:800:20C4:0`. La dirección de bucle invertido `0:0:0:0:0:0:0:1` en formato comprimido es `::`1. La dirección no especificada `0:0:0:0:0:0:0:0` en formato comprimido es `::`.

- **Formato mixto**. Este formato combina las direcciones IPv4 e IPv6. En este caso, el formato de dirección es n:n:n:n:n:n:d.d.d.d, donde cada n representa los valores hexadecimales de los seis elementos de dirección de 16 bits de orden superior de IPv6, y cada d representa el valor decimal de una dirección IPv4.

## <a name="address-types"></a>Tipos de dirección

Los bits iniciales de la dirección definen el tipo de dirección IPv6 específico. El campo de longitud variable que contiene estos bits iniciales se denomina prefijo de formato (FP).

Una dirección de unidifusión de IPv6 se divide en dos partes. La primera parte contiene el prefijo de dirección y la segunda parte contiene el identificador de interfaz. Una forma concisa de expresar una combinación de dirección y prefijo IPv6 es la siguiente: dirección ipv6/longitud de prefijo.

A continuación se muestra un ejemplo de una dirección con un prefijo de 64 bits.

`3FFE:FFFF:0:CD30:0:0:0:0/64`.

El prefijo de este ejemplo es `3FFE:FFFF:0:CD30`. La dirección también se puede escribir en formato comprimido, como `3FFE:FFFF:0:CD30::/64`.

IPv6 define los siguientes tipos de dirección:

- **Dirección de unidifusión**. Identificador de una única interfaz. Un paquete enviado a esta dirección se entrega a la interfaz identificada. Las direcciones de unidifusión se diferencian de las direcciones de multidifusión por el valor del octeto de orden superior. El octeto de orden superior de las direcciones de multidifusión tiene el valor hexadecimal de FF. Los demás valores de este octeto identifican una dirección de unidifusión. A continuación se muestran diferentes tipos de direcciones de unidifusión:

  - **Direcciones locales de vínculo**. Estas direcciones se usan en un único vínculo y tienen el formato siguiente: FE80::*IdentificadorDeInterfaz*. Las direcciones locales de vínculo se usan entre nodos en un vínculo para la configuración de dirección automática, la detección de equipos cercanos o cuando no hay enrutadores presentes. Las direcciones locales de vínculo se usan principalmente en el inicio y cuando el sistema todavía no ha adquirido direcciones de ámbito mayor.

  - **Direcciones locales de sitio**. Estas direcciones se usan en un único sitio y tienen el formato siguiente: FEC0::*IdentificadorDeSubred*:*IdentificadorDeInterfaz*. Las direcciones locales de sitio se usan para el direccionamiento dentro de un sitio sin necesidad de un prefijo global.

  - **Direcciones de unidifusión IPv6 globales**. Estas direcciones se pueden usar en Internet y tienen el formato siguiente: 010(FP, 3 bits) TLA ID (13 bits) Reserved (8 bits) NLA ID (24 bits) SLA ID (16 bits) *IdentificadorDeInterfaz* (64 bits).

- **Dirección de multidifusión**. Identificador para un conjunto de interfaces (normalmente pertenecientes a diferentes nodos). Un paquete enviado a esta dirección se entrega a todas las interfaces identificadas por la dirección. Los tipos de dirección de multidifusión sustituyen a las direcciones de difusión IPv4.

- **Dirección de difusión por proximidad**. Identificador para un conjunto de interfaces (normalmente pertenecientes a diferentes nodos). Un paquete enviado a esta dirección se entrega a una sola interfaz identificada por la dirección. Se trata de la interfaz más próxima identificada por la métrica de enrutamiento. Las direcciones de difusión por proximidad se toman del espacio de direcciones de unidifusión y no se pueden distinguir sintácticamente. La interfaz a la que se realiza el direccionamiento realiza la distinción entre las direcciones de unidifusión y de difusión por proximidad como una función de su configuración.

En general, un nodo siempre tiene una dirección local de vínculo. Podría tener una dirección local de sitio y una o varias direcciones globales.

## <a name="see-also"></a>Vea también

- [Protocolo de Internet versión 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)

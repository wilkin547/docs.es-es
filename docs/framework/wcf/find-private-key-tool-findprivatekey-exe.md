---
description: 'Más información acerca de: herramienta de búsqueda de clave privada (FindPrivateKey.exe)'
title: Herramienta de búsqueda de clave privada (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 1d87d19e17c1de89c13db6d7ca092eedf630e6ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793290"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>Herramienta de búsqueda de clave privada (FindPrivateKey.exe)

Esta herramienta de línea de comandos se puede utilizar para recuperar una clave privada de un almacén de certificados. Por ejemplo, *FindPrivateKey.exe* se puede utilizar para buscar la ubicación y el nombre del archivo de clave privada asociado a un certificado X. 509 concreto en el almacén de certificados.

> [!IMPORTANT]
> La herramienta FindPrivateKey se entrega como ejemplo de WCF. Para obtener más información sobre dónde encontrar el ejemplo y cómo compilarlo, vea [FindPrivateKey](./samples/findprivatekey.md).

## <a name="syntax"></a>Sintaxis

```console
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>Observaciones

Las tablas siguientes describen los argumentos y las opciones que se pueden utilizar con la herramienta de búsqueda de clave privada (FindPrivateKey.exe).

|Argumento|Descripción|
|--------------|-----------------|
|`storeName`|Nombre del almacén de certificados.|
|`storeLocation`|Ubicación del almacén de certificados.|

|Opción|Descripción|
|------------|-----------------|
|`/n <`*subjectName*`>`|Especifica el nombre de sujeto del certificado.|
|`/t <`*huella digital*`>`|Especifica la huella digital del certificado. Utilice Certmgr.exe para recuperar la huella digital del certificado.|
|`/f`|Sólo genera el nombre de archivo.|
|`/d`|Sólo genera el directorio.|
|`/a`|Genera el nombre de archivo absoluto.|

## <a name="examples"></a>Ejemplos

El siguiente comando recupera la clave privada de John Doe:

```console
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

El siguiente comando recupera la clave privada para el equipo local:

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```

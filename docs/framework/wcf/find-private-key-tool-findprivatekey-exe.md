---
title: Herramienta de búsqueda de clave privada (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 8f156cbb2f4fad8d51e356bd4dee2d72d9397ffb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>Herramienta de búsqueda de clave privada (FindPrivateKey.exe)

Esta herramienta de línea de comandos se puede utilizar para recuperar una clave privada de un almacén de certificados. Por ejemplo, *FindPrivateKey.exe* puede usarse para buscar la ubicación y el nombre del archivo de clave privada asociado con un certificado X.509 concreto en el almacén de certificados.

> [!IMPORTANT]
> La herramienta FindPrivateKey se entrega como ejemplo de WCF. Para obtener más información sobre dónde encontrar el ejemplo y cómo compilarlo, vea [FindPrivateKey](./samples/findprivatekey.md).

## <a name="syntax"></a>Sintaxis

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>Comentarios

Las tablas siguientes describen los argumentos y las opciones que se pueden utilizar con la herramienta de búsqueda de clave privada (FindPrivateKey.exe).

|Argumento|Descripción|
|--------------|-----------------|
|`storeName`|Nombre del almacén de certificados.|
|`storeLocation`|Ubicación del almacén de certificados.|

|Opción|Descripción|
|------------|-----------------|
|`/n <` *subjectName* `>`|Especifica el nombre de sujeto del certificado.|
|`/t <` *Huella digital* `>`|Especifica la huella digital del certificado. Utilice Certmgr.exe para recuperar la huella digital del certificado.|
|`/f`|Sólo genera el nombre de archivo.|
|`/d`|Sólo genera el directorio.|
|`/a`|Genera el nombre de archivo absoluto.|

## <a name="examples"></a>Ejemplos

El comando siguiente recupera la clave privada para John Doe:

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

El comando siguiente recupera la clave privada para el equipo local:

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
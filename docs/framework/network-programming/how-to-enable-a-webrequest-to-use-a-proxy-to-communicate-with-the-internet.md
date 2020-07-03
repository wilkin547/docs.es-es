---
title: Procedimiento para habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet
description: Obtenga información sobre cómo crear una instancia de proxy global con el fin de permitir que cualquier WebRequest use un proxy para comunicarse con Internet en .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502540"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Procedimiento para habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet

En este ejemplo se crea una instancia de proxy global que permitirá que cualquier <xref:System.Net.WebRequest> use un proxy para comunicarse con Internet. En el ejemplo se da por supuesto que el servidor proxy se denomina `webproxy` y que se comunica en el puerto 80, el puerto HTTP estándar.

## <a name="example"></a>Ejemplo

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) de C# para el espacio de nombres **System.Net**.
- Una [instrucción `Imports`](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)de Visual Basic para el espacio de nombres **System.Net**.

## <a name="see-also"></a>Vea también

- [Usar protocolos de aplicaciones](using-application-protocols.md)
- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)

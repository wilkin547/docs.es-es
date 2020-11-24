---
title: Manipulaciones de cadena básicas en .NET
description: Vea un ejemplo que llama a muchos métodos de cadena.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: e3e969520e068bde234c13d45ad790b76ecf8fdb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825162"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Procedimiento para realizar manipulaciones de cadena básicas en .NET

En el ejemplo siguiente, se usan algunos de los métodos descritos en los temas de [Operaciones básicas de cadenas](basic-string-operations.md) para construir una clase que realice manipulaciones de cadena de una manera que podría encontrarse en una aplicación real. La clase `MailToData` almacena el nombre y dirección de los individuos en propiedades distintas y proporciona una forma de combinar los campos `City`, `State` y `Zip` en una única cadena para mostrar al usuario. Además, la clase permite que el usuario escriba la información de ciudad, estado y código postal como una sola cadena. La aplicación analiza automáticamente la cadena única y escribe la información adecuada en la propiedad correspondiente.

Para simplificar, en este ejemplo se usa una aplicación de consola con una interfaz de línea de comandos.

## <a name="example"></a>Ejemplo

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]

Cuando se ejecuta el código anterior, se pide al usuario que escriba su nombre y dirección. La aplicación coloca la información en las propiedades adecuadas y muestra la información al usuario, creando una única cadena que muestra la información sobre la ciudad, el estado y el código postal.

## <a name="see-also"></a>Vea también

- [Operaciones básicas de cadenas](basic-string-operations.md)

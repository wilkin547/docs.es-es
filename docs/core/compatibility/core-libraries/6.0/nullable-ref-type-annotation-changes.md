---
title: 'Cambio importante: cambios de anotación en los tipos de referencia que aceptan valores NULL'
description: Obtenga información sobre el cambio importante de .NET 6.0 en las bibliotecas de .NET básicas, donde algunas anotaciones de tipo de referencia que aceptan valores NULL han cambiado.
ms.date: 02/11/2021
ms.openlocfilehash: a0133ce49ba33d0e835b718f3f2b19180526c61b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488254"
---
# <a name="changes-to-nullable-reference-type-annotations"></a>Cambios en las anotaciones de tipos de referencia que aceptan valores NULL

En .NET 6.0, algunas anotaciones de nulabilidad de las bibliotecas de .NET han cambiado.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, algunas anotaciones de tipos de referencia que aceptan valores NULL son incorrectas y las advertencias de compilación están ausentes o son incorrectas. A partir de .NET 6.0, se han actualizado algunas anotaciones aplicadas previamente. Se generarán nuevas advertencias de compilación y ya no se producirán advertencias de compilación incorrectas para las API afectadas.

Algunos de estos cambios se consideran *importantes*, ya que pueden dar lugar a nuevas advertencias en tiempo de compilación. Al realizar la migración a .NET 6.0, será necesario actualizar el código que hace referencia a estas API.

En esta página también se documentan otros cambios que no se consideran importantes. Cualquier código que haga referencia a las API actualizadas se puede beneficiar de la eliminación de operadores o pragmas que ya no sean necesarios.

## <a name="version-introduced"></a>Versión introducida

6.0

## <a name="reason-for-change"></a>Motivo del cambio

A partir de .NET Core 3.0, se han aplicado anotaciones de nulabilidad a las bibliotecas de .NET. Desde el principio del esfuerzo, se esperaban errores en estas anotaciones. Gracias a comentarios y pruebas adicionales, se ha determinado que las anotaciones que aceptan valores NULL de las API afectadas eran inexactas. Las anotaciones actualizadas representan correctamente los contratos de nulabilidad de las API.

## <a name="recommended-action"></a>Acción recomendada

Actualice el código que llama a estas API para reflejar los contratos de nulabilidad revisados.

## <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran las API afectadas:

| API | Qué cambia | Importante o no importante | Versión agregada |
| - | - | - |
| <xref:System.ComponentModel.ISite.Container?displayProperty=nameWithType> | Tipo de propiedad que admite un valor NULL | Problemático | Versión preliminar 1 |
| <xref:System.Xml.Linq.XContainer.Add(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XContainer.AddFirst(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XContainer.ReplaceNodes(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XDocument.%23ctor(System.Object[])> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XDocument.%23ctor(System.Xml.Linq.XDeclaration,System.Object[])> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XElement.%23ctor(System.Xml.Linq.XName,System.Object[])> | Segundo tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XElement.ReplaceAll(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XElement.ReplaceAttributes(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XNode.AddAfterSelf(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XNode.AddBeforeSelf(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XNode.ReplaceWith(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XStreamingElement.%23ctor(System.Xml.Linq.XName,System.Object)> | Segundo tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XStreamingElement.%23ctor(System.Xml.Linq.XName,System.Object[])> | Segundo tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Xml.Linq.XStreamingElement.Add(System.Object[])?displayProperty=nameWithType> | Tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Net.Http.HttpClient.PatchAsync%2A?displayProperty=nameWithType> | Tipo de parámetro `content` que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Net.Http.HttpClient.PostAsync%2A?displayProperty=nameWithType> | Tipo de parámetro `content` que admite un valor NULL  | No importante | Versión preliminar 1 |
| <xref:System.Net.Http.HttpClient.PutAsync%2A?displayProperty=nameWithType> | Tipo de parámetro `content` que admite un valor NULL  | No importante | Versión preliminar 1 |
| <xref:System.Linq.Expressions.MethodCallExpression.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.Expression})?displayProperty=nameWithType> | Primer tipo de parámetro que admite un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Linq.Expressions.Expression%601.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.ParameterExpression})?displayProperty=nameWithType> | Tipo de valor devuelto que no acepta un valor NULL | No importante | Versión preliminar 1 |
| <xref:System.Data.IDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> | Tipo de parámetro `buffer` que admite un valor NULL | Problemático | Versión preliminar 1 |
| <xref:System.Data.IDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType> | Tipo de parámetro `buffer` que admite un valor NULL | Problemático | Versión preliminar 1 |
| <xref:System.Data.Common.DbDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> | Tipo de parámetro `buffer` que admite un valor NULL | Problemático | Versión preliminar 1 |
| <xref:System.Data.Common.DbDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType> | Tipo de parámetro `buffer` que admite un valor NULL | Problemático | Versión preliminar 1 |

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.ComponentModel.ISite.Container`
- `M:System.Xml.Linq.XContainer.Add(System.Object[])`
- `M:System.Xml.Linq.XContainer.AddFirst(System.Object[])`
- `M:System.Xml.Linq.XContainer.ReplaceNodes(System.Object[])`
- `M:System.Xml.Linq.XDocument.#ctor(System.Object[])`
- `M:System.Xml.Linq.XDocument.#ctor(System.Xml.Linq.XDeclaration,System.Object[])`
- `M:System.Xml.Linq.XElement.#ctor(System.Xml.Linq.XName,System.Object[])`
- `M:System.Xml.Linq.XElement.ReplaceAll(System.Object[])`
- `M:System.Xml.Linq.XElement.ReplaceAttributes(System.Object[])`
- `M:System.Xml.Linq.XNode.AddAfterSelf(System.Object[])`
- `M:System.Xml.Linq.XNode.AddBeforeSelf(System.Object[])`
- `M:System.Xml.Linq.XNode.ReplaceWith(System.Object[])`
- `M:System.Xml.Linq.XStreamingElement.#ctor(System.Xml.Linq.XName,System.Object)`
- `M:System.Xml.Linq.XStreamingElement.#ctor(System.Xml.Linq.XName,System.Object[])`
- `M:System.Xml.Linq.XStreamingElement.Add(System.Object[])`
- `O:System.Net.Http.HttpClient.PatchAsync`
- `O:System.Net.Http.HttpClient.PostAsync`
- `O:System.Net.Http.HttpClient.PutAsync`
- `M:System.Linq.Expressions.MethodCallExpression.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.Expression})`
- `M:System.Linq.Expressions.Expression%601.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.ParameterExpression})`
- `M:System.Data.IDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)`
- `M:System.Data.IDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)`
- `M:System.Data.Common.DbDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)`
- `M:System.Data.Common.DbDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)`

-->

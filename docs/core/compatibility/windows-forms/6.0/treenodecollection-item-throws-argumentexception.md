---
title: 'Cambio importante: TreeNodeCollection.Item(Int32) produce una excepción ArgumentException para el nodo en uso.'
description: Obtenga información sobre el cambio importante en .NET 6.0 donde TreeNodeCollection.Item(Int32) ahora produce una excepción ArgumentException si el nodo que se está asignando ya está asignado a una vista de árbol.
ms.date: 01/19/2021
ms.openlocfilehash: efd6ca5d594b2aa64e10cce2cef6c0e1c411bb1e
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506527"
---
# <a name="treenodecollectionitem-throws-exception-if-node-is-assigned-elsewhere"></a>TreeNodeCollection.Item produce una excepción si el nodo se asigna en otro lugar.

<xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> produce <xref:System.ArgumentException> si el nodo que se está asignando ya está enlazado a otro valor <xref:System.Windows.Forms.TreeView> o a este <xref:System.Windows.Forms.TreeView> en un índice diferente.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, puede asignar un nodo de árbol a una colección incluso si ya está enlazado a un <xref:System.Windows.Forms.TreeView>. Esto puede provocar la duplicación de nodos. A partir de .NET 6.0, <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> produce <xref:System.ArgumentException> si el nodo que se está asignando ya está enlazado a otro valor <xref:System.Windows.Forms.TreeView> o a este <xref:System.Windows.Forms.TreeView> en un índice diferente.

## <a name="reason-for-change"></a>Motivo del cambio

La validación del parámetro de entrada es coherente con el comportamiento de otras API de `TreeNodeCollection`.

## <a name="version-introduced"></a>Versión introducida

.NET 6.0 (versión preliminar 1)

## <a name="recommended-action"></a>Acción recomendada

Asegúrese de desenlazar un valor `TreeNode` antes de asignarlo a la colección.

## <a name="affected-apis"></a>API afectadas

<xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->

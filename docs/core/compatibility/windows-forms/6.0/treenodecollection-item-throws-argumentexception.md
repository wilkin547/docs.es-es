---
title: 'Cambio importante: TreeNodeCollection.Item(Int32) produce una excepción ArgumentException para el nodo en uso.'
description: Obtenga información sobre el cambio importante en .NET 6 donde TreeNodeCollection.Item(Int32) ahora produce una excepción ArgumentException si el nodo que se está asignando ya está asignado a una vista de árbol.
ms.date: 01/19/2021
ms.openlocfilehash: 29727da2e4bc3d6ac89ed88819bf03d058603f77
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255702"
---
# <a name="treenodecollectionitem-throws-exception-if-node-is-assigned-elsewhere"></a><span data-ttu-id="f40da-103">TreeNodeCollection.Item produce una excepción si el nodo se asigna en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="f40da-103">TreeNodeCollection.Item throws exception if node is assigned elsewhere</span></span>

<span data-ttu-id="f40da-104"><xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> produce <xref:System.ArgumentException> si el nodo que se está asignando ya está enlazado a otro valor <xref:System.Windows.Forms.TreeView> o a este <xref:System.Windows.Forms.TreeView> en un índice diferente.</span><span class="sxs-lookup"><span data-stu-id="f40da-104"><xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> throws an <xref:System.ArgumentException> if the node being assigned is already bound to another <xref:System.Windows.Forms.TreeView> or to this <xref:System.Windows.Forms.TreeView> at a different index.</span></span>

## <a name="change-description"></a><span data-ttu-id="f40da-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f40da-105">Change description</span></span>

<span data-ttu-id="f40da-106">En versiones anteriores de .NET, puede asignar un nodo de árbol a una colección incluso si ya está enlazado a un <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="f40da-106">In previous .NET versions, you can assign a tree node to a collection even if it's already bound to a <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="f40da-107">Esto puede provocar la duplicación de nodos.</span><span class="sxs-lookup"><span data-stu-id="f40da-107">This can lead to duplicated nodes.</span></span> <span data-ttu-id="f40da-108">A partir de .NET 6, <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> produce <xref:System.ArgumentException> si el nodo que se está asignando ya está enlazado a otro valor <xref:System.Windows.Forms.TreeView> o a este <xref:System.Windows.Forms.TreeView> en un índice diferente.</span><span class="sxs-lookup"><span data-stu-id="f40da-108">Starting in .NET 6, <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> throws an <xref:System.ArgumentException> if the node being assigned is already bound to another <xref:System.Windows.Forms.TreeView> or to this <xref:System.Windows.Forms.TreeView> at a different index.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f40da-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f40da-109">Reason for change</span></span>

<span data-ttu-id="f40da-110">La validación del parámetro de entrada es coherente con el comportamiento de otras API de `TreeNodeCollection`.</span><span class="sxs-lookup"><span data-stu-id="f40da-110">Validating the input parameter is consistent with the behavior of other `TreeNodeCollection` APIs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f40da-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f40da-111">Version introduced</span></span>

<span data-ttu-id="f40da-112">.NET 6 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="f40da-112">.NET 6 Preview 1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f40da-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f40da-113">Recommended action</span></span>

<span data-ttu-id="f40da-114">Asegúrese de desenlazar un valor `TreeNode` antes de asignarlo a la colección.</span><span class="sxs-lookup"><span data-stu-id="f40da-114">Make sure to unbind a `TreeNode` before assigning it to the collection.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f40da-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f40da-115">Affected APIs</span></span>

<xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->

---
description: 'Más información sobre: método XmlReader. CreateSqlReader'
title: Método XmlReader. CreateSqlReader (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 61d594c0438c86863ce4052387439f5483d8a34c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740440"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="f20de-103">Método XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="f20de-103">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="f20de-104">Crea una nueva instancia <xref:System.Xml.XmlReader> con el flujo, la configuración y la información de contexto especificados para el análisis.</span><span class="sxs-lookup"><span data-stu-id="f20de-104">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="f20de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f20de-105">Parameters</span></span>

- <span data-ttu-id="f20de-106">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="f20de-106">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="f20de-107">Flujo que contiene los datos XML.</span><span class="sxs-lookup"><span data-stu-id="f20de-107">The stream that contains the XML data.</span></span>

- <span data-ttu-id="f20de-108">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="f20de-108">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="f20de-109">Configuración de la nueva instancia <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f20de-109">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="f20de-110">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="f20de-110">This value can be `null`.</span></span>

- <span data-ttu-id="f20de-111">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="f20de-111">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="f20de-112">Información de contexto necesaria para analizar el fragmento XML.</span><span class="sxs-lookup"><span data-stu-id="f20de-112">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="f20de-113">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="f20de-113">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="f20de-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="f20de-114">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="f20de-115">Objeto usado para leer los datos XML del flujo.</span><span class="sxs-lookup"><span data-stu-id="f20de-115">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="f20de-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f20de-116">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f20de-117">El `XmlReader.CreateSqlReader` método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="f20de-117">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f20de-118">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="f20de-118">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f20de-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f20de-119">Requirements</span></span>

<span data-ttu-id="f20de-120">**Espacio de nombres:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="f20de-120">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="f20de-121">**Ensamblado:** System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="f20de-121">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="f20de-122">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="f20de-122">**.NET Framework versions:** Available since 2.0.</span></span>

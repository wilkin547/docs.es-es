---
title: Método XmlReader.CreateSqlReader (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155744"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="ffbbd-102">Método XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="ffbbd-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="ffbbd-103">Crea una nueva instancia <xref:System.Xml.XmlReader> con el flujo, la configuración y la información de contexto especificados para el análisis.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="ffbbd-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ffbbd-104">Parameters</span></span>

- <span data-ttu-id="ffbbd-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="ffbbd-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="ffbbd-106">Flujo que contiene los datos XML.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="ffbbd-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="ffbbd-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="ffbbd-108">Configuración de la nueva instancia <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="ffbbd-109">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-109">This value can be `null`.</span></span>

- <span data-ttu-id="ffbbd-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="ffbbd-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="ffbbd-111">Información de contexto necesaria para analizar el fragmento XML.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="ffbbd-112">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="ffbbd-113">Devuelve</span><span class="sxs-lookup"><span data-stu-id="ffbbd-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="ffbbd-114">Objeto usado para leer los datos XML del flujo.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffbbd-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ffbbd-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ffbbd-116">El `XmlReader.CreateSqlReader` método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ffbbd-117">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ffbbd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffbbd-118">Requirements</span></span>

<span data-ttu-id="ffbbd-119">**Espacio de nombres:**<xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="ffbbd-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="ffbbd-120">**Montaje:** System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="ffbbd-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="ffbbd-121">**Versiones de .NET Framework:** Disponible desde 2.0.</span><span class="sxs-lookup"><span data-stu-id="ffbbd-121">**.NET Framework versions:** Available since 2.0.</span></span>

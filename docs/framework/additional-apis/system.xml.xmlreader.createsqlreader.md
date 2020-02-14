---
title: Método XmlReader. CreateSqlReader (System. xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: c65ef7c073175488c11c5e912a44d46fd4319209
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215446"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="d2511-102">Método XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="d2511-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="d2511-103">Crea una nueva instancia <xref:System.Xml.XmlReader> con el flujo, la configuración y la información de contexto especificados para el análisis.</span><span class="sxs-lookup"><span data-stu-id="d2511-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="d2511-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2511-104">Parameters</span></span>

- <span data-ttu-id="d2511-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="d2511-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="d2511-106">Flujo que contiene los datos XML.</span><span class="sxs-lookup"><span data-stu-id="d2511-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="d2511-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="d2511-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="d2511-108">Configuración de la nueva instancia <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d2511-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="d2511-109">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="d2511-109">This value can be `null`.</span></span>

- <span data-ttu-id="d2511-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="d2511-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="d2511-111">Información de contexto necesaria para analizar el fragmento XML.</span><span class="sxs-lookup"><span data-stu-id="d2511-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="d2511-112">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="d2511-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="d2511-113">Devuelve</span><span class="sxs-lookup"><span data-stu-id="d2511-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="d2511-114">Objeto usado para leer los datos XML del flujo.</span><span class="sxs-lookup"><span data-stu-id="d2511-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2511-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d2511-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d2511-116">El método `XmlReader.CreateSqlReader` es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="d2511-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d2511-117">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="d2511-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d2511-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2511-118">Requirements</span></span>

<span data-ttu-id="d2511-119">**Espacio de nombres:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="d2511-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="d2511-120">**Ensamblado:** System. Xml. dll</span><span class="sxs-lookup"><span data-stu-id="d2511-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="d2511-121">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="d2511-121">**.NET Framework versions:** Available since 2.0.</span></span>

---
title: Colecciones de esquemas de OLE DB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9b88308c5dad69ed1ba6f48f525931e94f13ef1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="7609f-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="7609f-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="7609f-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="7609f-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="7609f-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7609f-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="7609f-105">El controlador OLE DB de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="7609f-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7609f-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="7609f-106">Tables</span></span>  
  
-   <span data-ttu-id="7609f-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="7609f-107">Columns</span></span>  
  
-   <span data-ttu-id="7609f-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7609f-108">Procedures</span></span>  
  
-   <span data-ttu-id="7609f-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7609f-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7609f-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="7609f-110">Catalog</span></span>  
  
-   <span data-ttu-id="7609f-111">Índices</span><span class="sxs-lookup"><span data-stu-id="7609f-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7609f-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="7609f-112">Tables</span></span>  
  
|<span data-ttu-id="7609f-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-113">ColumnName</span></span>|<span data-ttu-id="7609f-114">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-115">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-116">String</span><span class="sxs-lookup"><span data-stu-id="7609f-116">String</span></span>|  
|<span data-ttu-id="7609f-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-118">String</span><span class="sxs-lookup"><span data-stu-id="7609f-118">String</span></span>|  
|<span data-ttu-id="7609f-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-119">TABLE_NAME</span></span>|<span data-ttu-id="7609f-120">String</span><span class="sxs-lookup"><span data-stu-id="7609f-120">String</span></span>|  
|<span data-ttu-id="7609f-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-121">TABLE_TYPE</span></span>|<span data-ttu-id="7609f-122">String</span><span class="sxs-lookup"><span data-stu-id="7609f-122">String</span></span>|  
|<span data-ttu-id="7609f-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-123">TABLE_GUID</span></span>|<span data-ttu-id="7609f-124">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-124">Guid</span></span>|  
|<span data-ttu-id="7609f-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-125">DESCRIPTION</span></span>|<span data-ttu-id="7609f-126">String</span><span class="sxs-lookup"><span data-stu-id="7609f-126">String</span></span>|  
|<span data-ttu-id="7609f-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-127">TABLE_PROPID</span></span>|<span data-ttu-id="7609f-128">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-128">Int64</span></span>|  
|<span data-ttu-id="7609f-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-129">DATE_CREATED</span></span>|<span data-ttu-id="7609f-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-130">DateTime</span></span>|  
|<span data-ttu-id="7609f-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-131">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7609f-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="7609f-133">Columns</span></span>  
  
|<span data-ttu-id="7609f-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-134">ColumnName</span></span>|<span data-ttu-id="7609f-135">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-136">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-137">String</span><span class="sxs-lookup"><span data-stu-id="7609f-137">String</span></span>|  
|<span data-ttu-id="7609f-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-139">String</span><span class="sxs-lookup"><span data-stu-id="7609f-139">String</span></span>|  
|<span data-ttu-id="7609f-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-140">TABLE_NAME</span></span>|<span data-ttu-id="7609f-141">String</span><span class="sxs-lookup"><span data-stu-id="7609f-141">String</span></span>|  
|<span data-ttu-id="7609f-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-142">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-143">String</span><span class="sxs-lookup"><span data-stu-id="7609f-143">String</span></span>|  
|<span data-ttu-id="7609f-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-144">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-145">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-145">Guid</span></span>|  
|<span data-ttu-id="7609f-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-146">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-147">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-147">Int64</span></span>|  
|<span data-ttu-id="7609f-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-149">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-149">Int64</span></span>|  
|<span data-ttu-id="7609f-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7609f-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-151">Boolean</span></span>|  
|<span data-ttu-id="7609f-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7609f-153">String</span><span class="sxs-lookup"><span data-stu-id="7609f-153">String</span></span>|  
|<span data-ttu-id="7609f-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7609f-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="7609f-155">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-155">Int64</span></span>|  
|<span data-ttu-id="7609f-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-156">IS_NULLABLE</span></span>|<span data-ttu-id="7609f-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-157">Boolean</span></span>|  
|<span data-ttu-id="7609f-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-158">DATA_TYPE</span></span>|<span data-ttu-id="7609f-159">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-159">Int32</span></span>|  
|<span data-ttu-id="7609f-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-160">TYPE_GUID</span></span>|<span data-ttu-id="7609f-161">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-161">Guid</span></span>|  
|<span data-ttu-id="7609f-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7609f-163">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-163">Int64</span></span>|  
|<span data-ttu-id="7609f-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7609f-165">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-165">Int64</span></span>|  
|<span data-ttu-id="7609f-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7609f-167">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-167">Int32</span></span>|  
|<span data-ttu-id="7609f-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7609f-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="7609f-169">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-169">Int16</span></span>|  
|<span data-ttu-id="7609f-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="7609f-171">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-171">Int64</span></span>|  
|<span data-ttu-id="7609f-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7609f-173">String</span><span class="sxs-lookup"><span data-stu-id="7609f-173">String</span></span>|  
|<span data-ttu-id="7609f-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7609f-175">String</span><span class="sxs-lookup"><span data-stu-id="7609f-175">String</span></span>|  
|<span data-ttu-id="7609f-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7609f-177">String</span><span class="sxs-lookup"><span data-stu-id="7609f-177">String</span></span>|  
|<span data-ttu-id="7609f-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="7609f-179">String</span><span class="sxs-lookup"><span data-stu-id="7609f-179">String</span></span>|  
|<span data-ttu-id="7609f-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7609f-181">String</span><span class="sxs-lookup"><span data-stu-id="7609f-181">String</span></span>|  
|<span data-ttu-id="7609f-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-182">COLLATION_NAME</span></span>|<span data-ttu-id="7609f-183">String</span><span class="sxs-lookup"><span data-stu-id="7609f-183">String</span></span>|  
|<span data-ttu-id="7609f-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7609f-185">String</span><span class="sxs-lookup"><span data-stu-id="7609f-185">String</span></span>|  
|<span data-ttu-id="7609f-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7609f-187">String</span><span class="sxs-lookup"><span data-stu-id="7609f-187">String</span></span>|  
|<span data-ttu-id="7609f-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-188">DOMAIN_NAME</span></span>|<span data-ttu-id="7609f-189">String</span><span class="sxs-lookup"><span data-stu-id="7609f-189">String</span></span>|  
|<span data-ttu-id="7609f-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-190">DESCRIPTION</span></span>|<span data-ttu-id="7609f-191">String</span><span class="sxs-lookup"><span data-stu-id="7609f-191">String</span></span>|  
|<span data-ttu-id="7609f-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="7609f-192">COLUMN_LCID</span></span>|<span data-ttu-id="7609f-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-193">Int32</span></span>|  
|<span data-ttu-id="7609f-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="7609f-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="7609f-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-195">Int32</span></span>|  
|<span data-ttu-id="7609f-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="7609f-196">COLUMN_SORTID</span></span>|<span data-ttu-id="7609f-197">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-197">Int32</span></span>|  
|<span data-ttu-id="7609f-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="7609f-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="7609f-199">Byte[]</span></span>|  
|<span data-ttu-id="7609f-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="7609f-200">IS_COMPUTED</span></span>|<span data-ttu-id="7609f-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7609f-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7609f-202">Procedures</span></span>  
  
|<span data-ttu-id="7609f-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-203">ColumnName</span></span>|<span data-ttu-id="7609f-204">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7609f-206">String</span><span class="sxs-lookup"><span data-stu-id="7609f-206">String</span></span>|  
|<span data-ttu-id="7609f-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7609f-208">String</span><span class="sxs-lookup"><span data-stu-id="7609f-208">String</span></span>|  
|<span data-ttu-id="7609f-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="7609f-210">String</span><span class="sxs-lookup"><span data-stu-id="7609f-210">String</span></span>|  
|<span data-ttu-id="7609f-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7609f-212">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-212">Int16</span></span>|  
|<span data-ttu-id="7609f-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7609f-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7609f-214">String</span><span class="sxs-lookup"><span data-stu-id="7609f-214">String</span></span>|  
|<span data-ttu-id="7609f-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-215">DESCRIPTION</span></span>|<span data-ttu-id="7609f-216">String</span><span class="sxs-lookup"><span data-stu-id="7609f-216">String</span></span>|  
|<span data-ttu-id="7609f-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-217">DATE_CREATED</span></span>|<span data-ttu-id="7609f-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-218">DateTime</span></span>|  
|<span data-ttu-id="7609f-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-219">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7609f-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7609f-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7609f-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-222">ColumnName</span></span>|<span data-ttu-id="7609f-223">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7609f-225">String</span><span class="sxs-lookup"><span data-stu-id="7609f-225">String</span></span>|  
|<span data-ttu-id="7609f-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7609f-227">String</span><span class="sxs-lookup"><span data-stu-id="7609f-227">String</span></span>|  
|<span data-ttu-id="7609f-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="7609f-229">String</span><span class="sxs-lookup"><span data-stu-id="7609f-229">String</span></span>|  
|<span data-ttu-id="7609f-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-230">PARAMETER_NAME</span></span>|<span data-ttu-id="7609f-231">String</span><span class="sxs-lookup"><span data-stu-id="7609f-231">String</span></span>|  
|<span data-ttu-id="7609f-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-233">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-233">Int32</span></span>|  
|<span data-ttu-id="7609f-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="7609f-235">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-235">Int32</span></span>|  
|<span data-ttu-id="7609f-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="7609f-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-237">Boolean</span></span>|  
|<span data-ttu-id="7609f-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="7609f-239">String</span><span class="sxs-lookup"><span data-stu-id="7609f-239">String</span></span>|  
|<span data-ttu-id="7609f-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-240">IS_NULLABLE</span></span>|<span data-ttu-id="7609f-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-241">Boolean</span></span>|  
|<span data-ttu-id="7609f-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-242">DATA_TYPE</span></span>|<span data-ttu-id="7609f-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-243">Int32</span></span>|  
|<span data-ttu-id="7609f-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7609f-245">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-245">Int64</span></span>|  
|<span data-ttu-id="7609f-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7609f-247">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-247">Int64</span></span>|  
|<span data-ttu-id="7609f-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7609f-249">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-249">Int32</span></span>|  
|<span data-ttu-id="7609f-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7609f-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="7609f-251">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-251">Int16</span></span>|  
|<span data-ttu-id="7609f-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-252">DESCRIPTION</span></span>|<span data-ttu-id="7609f-253">String</span><span class="sxs-lookup"><span data-stu-id="7609f-253">String</span></span>|  
|<span data-ttu-id="7609f-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-254">TYPE_NAME</span></span>|<span data-ttu-id="7609f-255">String</span><span class="sxs-lookup"><span data-stu-id="7609f-255">String</span></span>|  
|<span data-ttu-id="7609f-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="7609f-257">String</span><span class="sxs-lookup"><span data-stu-id="7609f-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="7609f-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="7609f-258">Catalog</span></span>  
  
|<span data-ttu-id="7609f-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-259">ColumnName</span></span>|<span data-ttu-id="7609f-260">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-261">CATALOG_NAME</span></span>|<span data-ttu-id="7609f-262">String</span><span class="sxs-lookup"><span data-stu-id="7609f-262">String</span></span>|  
|<span data-ttu-id="7609f-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-263">DESCRIPTION</span></span>|<span data-ttu-id="7609f-264">String</span><span class="sxs-lookup"><span data-stu-id="7609f-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7609f-265">Índices</span><span class="sxs-lookup"><span data-stu-id="7609f-265">Indexes</span></span>  
  
|<span data-ttu-id="7609f-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-266">ColumnName</span></span>|<span data-ttu-id="7609f-267">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-268">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-269">String</span><span class="sxs-lookup"><span data-stu-id="7609f-269">String</span></span>|  
|<span data-ttu-id="7609f-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-271">String</span><span class="sxs-lookup"><span data-stu-id="7609f-271">String</span></span>|  
|<span data-ttu-id="7609f-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-272">TABLE_NAME</span></span>|<span data-ttu-id="7609f-273">String</span><span class="sxs-lookup"><span data-stu-id="7609f-273">String</span></span>|  
|<span data-ttu-id="7609f-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-274">INDEX_CATALOG</span></span>|<span data-ttu-id="7609f-275">String</span><span class="sxs-lookup"><span data-stu-id="7609f-275">String</span></span>|  
|<span data-ttu-id="7609f-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="7609f-277">String</span><span class="sxs-lookup"><span data-stu-id="7609f-277">String</span></span>|  
|<span data-ttu-id="7609f-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-278">INDEX_NAME</span></span>|<span data-ttu-id="7609f-279">String</span><span class="sxs-lookup"><span data-stu-id="7609f-279">String</span></span>|  
|<span data-ttu-id="7609f-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7609f-280">PRIMARY_KEY</span></span>|<span data-ttu-id="7609f-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-281">Boolean</span></span>|  
|<span data-ttu-id="7609f-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7609f-282">UNIQUE</span></span>|<span data-ttu-id="7609f-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-283">Boolean</span></span>|  
|<span data-ttu-id="7609f-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7609f-284">CLUSTERED</span></span>|<span data-ttu-id="7609f-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-285">Boolean</span></span>|  
|<span data-ttu-id="7609f-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-286">TYPE</span></span>|<span data-ttu-id="7609f-287">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-287">Int32</span></span>|  
|<span data-ttu-id="7609f-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7609f-288">FILL_FACTOR</span></span>|<span data-ttu-id="7609f-289">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-289">Int32</span></span>|  
|<span data-ttu-id="7609f-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7609f-290">INITIAL_SIZE</span></span>|<span data-ttu-id="7609f-291">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-291">Int32</span></span>|  
|<span data-ttu-id="7609f-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="7609f-292">NULLS</span></span>|<span data-ttu-id="7609f-293">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-293">Int32</span></span>|  
|<span data-ttu-id="7609f-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7609f-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7609f-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-295">Boolean</span></span>|  
|<span data-ttu-id="7609f-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7609f-296">AUTO_UPDATE</span></span>|<span data-ttu-id="7609f-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-297">Boolean</span></span>|  
|<span data-ttu-id="7609f-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-298">NULL_COLLATION</span></span>|<span data-ttu-id="7609f-299">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-299">Int32</span></span>|  
|<span data-ttu-id="7609f-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-301">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-301">Int64</span></span>|  
|<span data-ttu-id="7609f-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-302">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-303">String</span><span class="sxs-lookup"><span data-stu-id="7609f-303">String</span></span>|  
|<span data-ttu-id="7609f-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-304">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-305">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-305">Guid</span></span>|  
|<span data-ttu-id="7609f-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-306">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-307">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-307">Int64</span></span>|  
|<span data-ttu-id="7609f-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-308">COLLATION</span></span>|<span data-ttu-id="7609f-309">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-309">Int16</span></span>|  
|<span data-ttu-id="7609f-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7609f-310">CARDINALITY</span></span>|<span data-ttu-id="7609f-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="7609f-311">Decimal</span></span>|  
|<span data-ttu-id="7609f-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="7609f-312">PAGES</span></span>|<span data-ttu-id="7609f-313">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-313">Int32</span></span>|  
|<span data-ttu-id="7609f-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7609f-314">FILTER_CONDITION</span></span>|<span data-ttu-id="7609f-315">String</span><span class="sxs-lookup"><span data-stu-id="7609f-315">String</span></span>|  
|<span data-ttu-id="7609f-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7609f-316">INTEGRATED</span></span>|<span data-ttu-id="7609f-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="7609f-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="7609f-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="7609f-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="7609f-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7609f-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="7609f-320">Tables</span></span>  
  
-   <span data-ttu-id="7609f-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="7609f-321">Columns</span></span>  
  
-   <span data-ttu-id="7609f-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7609f-322">Procedures</span></span>  
  
-   <span data-ttu-id="7609f-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7609f-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7609f-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7609f-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7609f-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="7609f-325">Views</span></span>  
  
-   <span data-ttu-id="7609f-326">Índices</span><span class="sxs-lookup"><span data-stu-id="7609f-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7609f-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="7609f-327">Tables</span></span>  
  
|<span data-ttu-id="7609f-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-328">ColumnName</span></span>|<span data-ttu-id="7609f-329">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-330">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-331">String</span><span class="sxs-lookup"><span data-stu-id="7609f-331">String</span></span>|  
|<span data-ttu-id="7609f-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-333">String</span><span class="sxs-lookup"><span data-stu-id="7609f-333">String</span></span>|  
|<span data-ttu-id="7609f-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-334">TABLE_NAME</span></span>|<span data-ttu-id="7609f-335">String</span><span class="sxs-lookup"><span data-stu-id="7609f-335">String</span></span>|  
|<span data-ttu-id="7609f-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-336">TABLE_TYPE</span></span>|<span data-ttu-id="7609f-337">String</span><span class="sxs-lookup"><span data-stu-id="7609f-337">String</span></span>|  
|<span data-ttu-id="7609f-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-338">TABLE_GUID</span></span>|<span data-ttu-id="7609f-339">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-339">Guid</span></span>|  
|<span data-ttu-id="7609f-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-340">DESCRIPTION</span></span>|<span data-ttu-id="7609f-341">String</span><span class="sxs-lookup"><span data-stu-id="7609f-341">String</span></span>|  
|<span data-ttu-id="7609f-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-342">TABLE_PROPID</span></span>|<span data-ttu-id="7609f-343">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-343">Int64</span></span>|  
|<span data-ttu-id="7609f-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-344">DATE_CREATED</span></span>|<span data-ttu-id="7609f-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-345">DateTime</span></span>|  
|<span data-ttu-id="7609f-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-346">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7609f-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="7609f-348">Columns</span></span>  
  
|<span data-ttu-id="7609f-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-349">ColumnName</span></span>|<span data-ttu-id="7609f-350">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-351">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-352">String</span><span class="sxs-lookup"><span data-stu-id="7609f-352">String</span></span>|  
|<span data-ttu-id="7609f-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-354">String</span><span class="sxs-lookup"><span data-stu-id="7609f-354">String</span></span>|  
|<span data-ttu-id="7609f-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-355">TABLE_NAME</span></span>|<span data-ttu-id="7609f-356">String</span><span class="sxs-lookup"><span data-stu-id="7609f-356">String</span></span>|  
|<span data-ttu-id="7609f-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-357">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-358">String</span><span class="sxs-lookup"><span data-stu-id="7609f-358">String</span></span>|  
|<span data-ttu-id="7609f-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-359">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-360">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-360">Guid</span></span>|  
|<span data-ttu-id="7609f-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-361">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-362">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-362">Int64</span></span>|  
|<span data-ttu-id="7609f-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-364">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-364">Int64</span></span>|  
|<span data-ttu-id="7609f-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7609f-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-366">Boolean</span></span>|  
|<span data-ttu-id="7609f-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7609f-368">String</span><span class="sxs-lookup"><span data-stu-id="7609f-368">String</span></span>|  
|<span data-ttu-id="7609f-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7609f-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="7609f-370">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-370">Int64</span></span>|  
|<span data-ttu-id="7609f-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-371">IS_NULLABLE</span></span>|<span data-ttu-id="7609f-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-372">Boolean</span></span>|  
|<span data-ttu-id="7609f-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-373">DATA_TYPE</span></span>|<span data-ttu-id="7609f-374">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-374">Int32</span></span>|  
|<span data-ttu-id="7609f-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-375">TYPE_GUID</span></span>|<span data-ttu-id="7609f-376">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-376">Guid</span></span>|  
|<span data-ttu-id="7609f-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7609f-378">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-378">Int64</span></span>|  
|<span data-ttu-id="7609f-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7609f-380">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-380">Int64</span></span>|  
|<span data-ttu-id="7609f-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7609f-382">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-382">Int32</span></span>|  
|<span data-ttu-id="7609f-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7609f-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="7609f-384">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-384">Int16</span></span>|  
|<span data-ttu-id="7609f-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="7609f-386">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-386">Int64</span></span>|  
|<span data-ttu-id="7609f-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7609f-388">String</span><span class="sxs-lookup"><span data-stu-id="7609f-388">String</span></span>|  
|<span data-ttu-id="7609f-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7609f-390">String</span><span class="sxs-lookup"><span data-stu-id="7609f-390">String</span></span>|  
|<span data-ttu-id="7609f-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7609f-392">String</span><span class="sxs-lookup"><span data-stu-id="7609f-392">String</span></span>|  
|<span data-ttu-id="7609f-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="7609f-394">String</span><span class="sxs-lookup"><span data-stu-id="7609f-394">String</span></span>|  
|<span data-ttu-id="7609f-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7609f-396">String</span><span class="sxs-lookup"><span data-stu-id="7609f-396">String</span></span>|  
|<span data-ttu-id="7609f-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-397">COLLATION_NAME</span></span>|<span data-ttu-id="7609f-398">String</span><span class="sxs-lookup"><span data-stu-id="7609f-398">String</span></span>|  
|<span data-ttu-id="7609f-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7609f-400">String</span><span class="sxs-lookup"><span data-stu-id="7609f-400">String</span></span>|  
|<span data-ttu-id="7609f-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7609f-402">String</span><span class="sxs-lookup"><span data-stu-id="7609f-402">String</span></span>|  
|<span data-ttu-id="7609f-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-403">DOMAIN_NAME</span></span>|<span data-ttu-id="7609f-404">String</span><span class="sxs-lookup"><span data-stu-id="7609f-404">String</span></span>|  
|<span data-ttu-id="7609f-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-405">DESCRIPTION</span></span>|<span data-ttu-id="7609f-406">String</span><span class="sxs-lookup"><span data-stu-id="7609f-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7609f-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7609f-407">Procedures</span></span>  
  
|<span data-ttu-id="7609f-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-408">ColumnName</span></span>|<span data-ttu-id="7609f-409">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7609f-411">String</span><span class="sxs-lookup"><span data-stu-id="7609f-411">String</span></span>|  
|<span data-ttu-id="7609f-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7609f-413">String</span><span class="sxs-lookup"><span data-stu-id="7609f-413">String</span></span>|  
|<span data-ttu-id="7609f-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="7609f-415">String</span><span class="sxs-lookup"><span data-stu-id="7609f-415">String</span></span>|  
|<span data-ttu-id="7609f-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7609f-417">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-417">Int16</span></span>|  
|<span data-ttu-id="7609f-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7609f-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7609f-419">String</span><span class="sxs-lookup"><span data-stu-id="7609f-419">String</span></span>|  
|<span data-ttu-id="7609f-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-420">DESCRIPTION</span></span>|<span data-ttu-id="7609f-421">String</span><span class="sxs-lookup"><span data-stu-id="7609f-421">String</span></span>|  
|<span data-ttu-id="7609f-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-422">DATE_CREATED</span></span>|<span data-ttu-id="7609f-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-423">DateTime</span></span>|  
|<span data-ttu-id="7609f-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-424">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7609f-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7609f-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7609f-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-427">ColumnName</span></span>|<span data-ttu-id="7609f-428">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7609f-430">String</span><span class="sxs-lookup"><span data-stu-id="7609f-430">String</span></span>|  
|<span data-ttu-id="7609f-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7609f-432">String</span><span class="sxs-lookup"><span data-stu-id="7609f-432">String</span></span>|  
|<span data-ttu-id="7609f-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="7609f-434">String</span><span class="sxs-lookup"><span data-stu-id="7609f-434">String</span></span>|  
|<span data-ttu-id="7609f-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-435">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-436">String</span><span class="sxs-lookup"><span data-stu-id="7609f-436">String</span></span>|  
|<span data-ttu-id="7609f-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-437">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-438">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-438">Guid</span></span>|  
|<span data-ttu-id="7609f-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-439">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-440">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-440">Int64</span></span>|  
|<span data-ttu-id="7609f-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="7609f-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="7609f-442">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-442">Int64</span></span>|  
|<span data-ttu-id="7609f-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-444">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-444">Int64</span></span>|  
|<span data-ttu-id="7609f-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-445">IS_NULLABLE</span></span>|<span data-ttu-id="7609f-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-446">Boolean</span></span>|  
|<span data-ttu-id="7609f-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-447">DATA_TYPE</span></span>|<span data-ttu-id="7609f-448">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-448">Int32</span></span>|  
|<span data-ttu-id="7609f-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-449">TYPE_GUID</span></span>|<span data-ttu-id="7609f-450">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-450">Guid</span></span>|  
|<span data-ttu-id="7609f-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7609f-452">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-452">Int64</span></span>|  
|<span data-ttu-id="7609f-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7609f-454">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-454">Int64</span></span>|  
|<span data-ttu-id="7609f-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7609f-456">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-456">Int32</span></span>|  
|<span data-ttu-id="7609f-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7609f-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="7609f-458">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-458">Int16</span></span>|  
|<span data-ttu-id="7609f-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-459">DESCRIPTION</span></span>|<span data-ttu-id="7609f-460">String</span><span class="sxs-lookup"><span data-stu-id="7609f-460">String</span></span>|  
|<span data-ttu-id="7609f-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7609f-461">OVERLOAD</span></span>|<span data-ttu-id="7609f-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7609f-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="7609f-463">Views</span></span>  
  
|<span data-ttu-id="7609f-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-464">ColumnName</span></span>|<span data-ttu-id="7609f-465">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-466">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-467">String</span><span class="sxs-lookup"><span data-stu-id="7609f-467">String</span></span>|  
|<span data-ttu-id="7609f-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-469">String</span><span class="sxs-lookup"><span data-stu-id="7609f-469">String</span></span>|  
|<span data-ttu-id="7609f-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-470">TABLE_NAME</span></span>|<span data-ttu-id="7609f-471">String</span><span class="sxs-lookup"><span data-stu-id="7609f-471">String</span></span>|  
|<span data-ttu-id="7609f-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7609f-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="7609f-473">String</span><span class="sxs-lookup"><span data-stu-id="7609f-473">String</span></span>|  
|<span data-ttu-id="7609f-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-474">CHECK_OPTION</span></span>|<span data-ttu-id="7609f-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-475">Boolean</span></span>|  
|<span data-ttu-id="7609f-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-476">IS_UPDATABLE</span></span>|<span data-ttu-id="7609f-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-477">Boolean</span></span>|  
|<span data-ttu-id="7609f-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-478">DESCRIPTION</span></span>|<span data-ttu-id="7609f-479">String</span><span class="sxs-lookup"><span data-stu-id="7609f-479">String</span></span>|  
|<span data-ttu-id="7609f-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-480">DATE_CREATED</span></span>|<span data-ttu-id="7609f-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-481">DateTime</span></span>|  
|<span data-ttu-id="7609f-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-482">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7609f-484">Índices</span><span class="sxs-lookup"><span data-stu-id="7609f-484">Indexes</span></span>  
  
|<span data-ttu-id="7609f-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-485">ColumnName</span></span>|<span data-ttu-id="7609f-486">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-487">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-488">String</span><span class="sxs-lookup"><span data-stu-id="7609f-488">String</span></span>|  
|<span data-ttu-id="7609f-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-490">String</span><span class="sxs-lookup"><span data-stu-id="7609f-490">String</span></span>|  
|<span data-ttu-id="7609f-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-491">TABLE_NAME</span></span>|<span data-ttu-id="7609f-492">String</span><span class="sxs-lookup"><span data-stu-id="7609f-492">String</span></span>|  
|<span data-ttu-id="7609f-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-493">INDEX_CATALOG</span></span>|<span data-ttu-id="7609f-494">String</span><span class="sxs-lookup"><span data-stu-id="7609f-494">String</span></span>|  
|<span data-ttu-id="7609f-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="7609f-496">String</span><span class="sxs-lookup"><span data-stu-id="7609f-496">String</span></span>|  
|<span data-ttu-id="7609f-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-497">INDEX_NAME</span></span>|<span data-ttu-id="7609f-498">String</span><span class="sxs-lookup"><span data-stu-id="7609f-498">String</span></span>|  
|<span data-ttu-id="7609f-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7609f-499">PRIMARY_KEY</span></span>|<span data-ttu-id="7609f-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-500">Boolean</span></span>|  
|<span data-ttu-id="7609f-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7609f-501">UNIQUE</span></span>|<span data-ttu-id="7609f-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-502">Boolean</span></span>|  
|<span data-ttu-id="7609f-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7609f-503">CLUSTERED</span></span>|<span data-ttu-id="7609f-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-504">Boolean</span></span>|  
|<span data-ttu-id="7609f-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-505">TYPE</span></span>|<span data-ttu-id="7609f-506">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-506">Int32</span></span>|  
|<span data-ttu-id="7609f-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7609f-507">FILL_FACTOR</span></span>|<span data-ttu-id="7609f-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-508">Int32</span></span>|  
|<span data-ttu-id="7609f-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7609f-509">INITIAL_SIZE</span></span>|<span data-ttu-id="7609f-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-510">Int32</span></span>|  
|<span data-ttu-id="7609f-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="7609f-511">NULLS</span></span>|<span data-ttu-id="7609f-512">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-512">Int32</span></span>|  
|<span data-ttu-id="7609f-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7609f-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7609f-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-514">Boolean</span></span>|  
|<span data-ttu-id="7609f-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7609f-515">AUTO_UPDATE</span></span>|<span data-ttu-id="7609f-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-516">Boolean</span></span>|  
|<span data-ttu-id="7609f-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-517">NULL_COLLATION</span></span>|<span data-ttu-id="7609f-518">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-518">Int32</span></span>|  
|<span data-ttu-id="7609f-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-520">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-520">Int64</span></span>|  
|<span data-ttu-id="7609f-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-521">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-522">String</span><span class="sxs-lookup"><span data-stu-id="7609f-522">String</span></span>|  
|<span data-ttu-id="7609f-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-523">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-524">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-524">Guid</span></span>|  
|<span data-ttu-id="7609f-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-525">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-526">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-526">Int64</span></span>|  
|<span data-ttu-id="7609f-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-527">COLLATION</span></span>|<span data-ttu-id="7609f-528">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-528">Int16</span></span>|  
|<span data-ttu-id="7609f-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7609f-529">CARDINALITY</span></span>|<span data-ttu-id="7609f-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="7609f-530">Decimal</span></span>|  
|<span data-ttu-id="7609f-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="7609f-531">PAGES</span></span>|<span data-ttu-id="7609f-532">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-532">Int32</span></span>|  
|<span data-ttu-id="7609f-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7609f-533">FILTER_CONDITION</span></span>|<span data-ttu-id="7609f-534">String</span><span class="sxs-lookup"><span data-stu-id="7609f-534">String</span></span>|  
|<span data-ttu-id="7609f-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7609f-535">INTEGRATED</span></span>|<span data-ttu-id="7609f-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="7609f-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="7609f-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="7609f-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="7609f-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7609f-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="7609f-539">Tables</span></span>  
  
-   <span data-ttu-id="7609f-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="7609f-540">Columns</span></span>  
  
-   <span data-ttu-id="7609f-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7609f-541">Procedures</span></span>  
  
-   <span data-ttu-id="7609f-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="7609f-542">Views</span></span>  
  
-   <span data-ttu-id="7609f-543">Índices</span><span class="sxs-lookup"><span data-stu-id="7609f-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7609f-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="7609f-544">Tables</span></span>  
  
|<span data-ttu-id="7609f-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-545">ColumnName</span></span>|<span data-ttu-id="7609f-546">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-547">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-548">String</span><span class="sxs-lookup"><span data-stu-id="7609f-548">String</span></span>|  
|<span data-ttu-id="7609f-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-550">String</span><span class="sxs-lookup"><span data-stu-id="7609f-550">String</span></span>|  
|<span data-ttu-id="7609f-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-551">TABLE_NAME</span></span>|<span data-ttu-id="7609f-552">String</span><span class="sxs-lookup"><span data-stu-id="7609f-552">String</span></span>|  
|<span data-ttu-id="7609f-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-553">TABLE_TYPE</span></span>|<span data-ttu-id="7609f-554">String</span><span class="sxs-lookup"><span data-stu-id="7609f-554">String</span></span>|  
|<span data-ttu-id="7609f-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-555">TABLE_GUID</span></span>|<span data-ttu-id="7609f-556">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-556">Guid</span></span>|  
|<span data-ttu-id="7609f-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-557">DESCRIPTION</span></span>|<span data-ttu-id="7609f-558">String</span><span class="sxs-lookup"><span data-stu-id="7609f-558">String</span></span>|  
|<span data-ttu-id="7609f-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-559">TABLE_PROPID</span></span>|<span data-ttu-id="7609f-560">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-560">Int64</span></span>|  
|<span data-ttu-id="7609f-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-561">DATE_CREATED</span></span>|<span data-ttu-id="7609f-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-562">DateTime</span></span>|  
|<span data-ttu-id="7609f-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-563">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7609f-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="7609f-565">Columns</span></span>  
  
|<span data-ttu-id="7609f-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-566">ColumnName</span></span>|<span data-ttu-id="7609f-567">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-568">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-569">String</span><span class="sxs-lookup"><span data-stu-id="7609f-569">String</span></span>|  
|<span data-ttu-id="7609f-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-571">String</span><span class="sxs-lookup"><span data-stu-id="7609f-571">String</span></span>|  
|<span data-ttu-id="7609f-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-572">TABLE_NAME</span></span>|<span data-ttu-id="7609f-573">String</span><span class="sxs-lookup"><span data-stu-id="7609f-573">String</span></span>|  
|<span data-ttu-id="7609f-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-574">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-575">String</span><span class="sxs-lookup"><span data-stu-id="7609f-575">String</span></span>|  
|<span data-ttu-id="7609f-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-576">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-577">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-577">Guid</span></span>|  
|<span data-ttu-id="7609f-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-578">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-579">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-579">Int64</span></span>|  
|<span data-ttu-id="7609f-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-581">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-581">Int64</span></span>|  
|<span data-ttu-id="7609f-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7609f-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-583">Boolean</span></span>|  
|<span data-ttu-id="7609f-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7609f-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7609f-585">String</span><span class="sxs-lookup"><span data-stu-id="7609f-585">String</span></span>|  
|<span data-ttu-id="7609f-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7609f-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="7609f-587">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-587">Int64</span></span>|  
|<span data-ttu-id="7609f-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-588">IS_NULLABLE</span></span>|<span data-ttu-id="7609f-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-589">Boolean</span></span>|  
|<span data-ttu-id="7609f-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-590">DATA_TYPE</span></span>|<span data-ttu-id="7609f-591">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-591">Int32</span></span>|  
|<span data-ttu-id="7609f-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-592">TYPE_GUID</span></span>|<span data-ttu-id="7609f-593">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-593">Guid</span></span>|  
|<span data-ttu-id="7609f-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7609f-595">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-595">Int64</span></span>|  
|<span data-ttu-id="7609f-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7609f-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7609f-597">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-597">Int64</span></span>|  
|<span data-ttu-id="7609f-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7609f-599">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-599">Int32</span></span>|  
|<span data-ttu-id="7609f-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7609f-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="7609f-601">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-601">Int16</span></span>|  
|<span data-ttu-id="7609f-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7609f-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="7609f-603">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-603">Int64</span></span>|  
|<span data-ttu-id="7609f-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7609f-605">String</span><span class="sxs-lookup"><span data-stu-id="7609f-605">String</span></span>|  
|<span data-ttu-id="7609f-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7609f-607">String</span><span class="sxs-lookup"><span data-stu-id="7609f-607">String</span></span>|  
|<span data-ttu-id="7609f-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7609f-609">String</span><span class="sxs-lookup"><span data-stu-id="7609f-609">String</span></span>|  
|<span data-ttu-id="7609f-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="7609f-611">String</span><span class="sxs-lookup"><span data-stu-id="7609f-611">String</span></span>|  
|<span data-ttu-id="7609f-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7609f-613">String</span><span class="sxs-lookup"><span data-stu-id="7609f-613">String</span></span>|  
|<span data-ttu-id="7609f-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-614">COLLATION_NAME</span></span>|<span data-ttu-id="7609f-615">String</span><span class="sxs-lookup"><span data-stu-id="7609f-615">String</span></span>|  
|<span data-ttu-id="7609f-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7609f-617">String</span><span class="sxs-lookup"><span data-stu-id="7609f-617">String</span></span>|  
|<span data-ttu-id="7609f-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7609f-619">String</span><span class="sxs-lookup"><span data-stu-id="7609f-619">String</span></span>|  
|<span data-ttu-id="7609f-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-620">DOMAIN_NAME</span></span>|<span data-ttu-id="7609f-621">String</span><span class="sxs-lookup"><span data-stu-id="7609f-621">String</span></span>|  
|<span data-ttu-id="7609f-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-622">DESCRIPTION</span></span>|<span data-ttu-id="7609f-623">String</span><span class="sxs-lookup"><span data-stu-id="7609f-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7609f-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7609f-624">Procedures</span></span>  
  
|<span data-ttu-id="7609f-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-625">ColumnName</span></span>|<span data-ttu-id="7609f-626">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7609f-628">String</span><span class="sxs-lookup"><span data-stu-id="7609f-628">String</span></span>|  
|<span data-ttu-id="7609f-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7609f-630">String</span><span class="sxs-lookup"><span data-stu-id="7609f-630">String</span></span>|  
|<span data-ttu-id="7609f-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="7609f-632">String</span><span class="sxs-lookup"><span data-stu-id="7609f-632">String</span></span>|  
|<span data-ttu-id="7609f-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7609f-634">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-634">Int16</span></span>|  
|<span data-ttu-id="7609f-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7609f-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7609f-636">String</span><span class="sxs-lookup"><span data-stu-id="7609f-636">String</span></span>|  
|<span data-ttu-id="7609f-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-637">DESCRIPTION</span></span>|<span data-ttu-id="7609f-638">String</span><span class="sxs-lookup"><span data-stu-id="7609f-638">String</span></span>|  
|<span data-ttu-id="7609f-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-639">DATE_CREATED</span></span>|<span data-ttu-id="7609f-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-640">DateTime</span></span>|  
|<span data-ttu-id="7609f-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-641">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7609f-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="7609f-643">Views</span></span>  
  
|<span data-ttu-id="7609f-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-644">ColumnName</span></span>|<span data-ttu-id="7609f-645">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-646">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-647">String</span><span class="sxs-lookup"><span data-stu-id="7609f-647">String</span></span>|  
|<span data-ttu-id="7609f-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-649">String</span><span class="sxs-lookup"><span data-stu-id="7609f-649">String</span></span>|  
|<span data-ttu-id="7609f-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-650">TABLE_NAME</span></span>|<span data-ttu-id="7609f-651">String</span><span class="sxs-lookup"><span data-stu-id="7609f-651">String</span></span>|  
|<span data-ttu-id="7609f-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7609f-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="7609f-653">String</span><span class="sxs-lookup"><span data-stu-id="7609f-653">String</span></span>|  
|<span data-ttu-id="7609f-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-654">CHECK_OPTION</span></span>|<span data-ttu-id="7609f-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-655">Boolean</span></span>|  
|<span data-ttu-id="7609f-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7609f-656">IS_UPDATABLE</span></span>|<span data-ttu-id="7609f-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-657">Boolean</span></span>|  
|<span data-ttu-id="7609f-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7609f-658">DESCRIPTION</span></span>|<span data-ttu-id="7609f-659">String</span><span class="sxs-lookup"><span data-stu-id="7609f-659">String</span></span>|  
|<span data-ttu-id="7609f-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7609f-660">DATE_CREATED</span></span>|<span data-ttu-id="7609f-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-661">DateTime</span></span>|  
|<span data-ttu-id="7609f-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7609f-662">DATE_MODIFIED</span></span>|<span data-ttu-id="7609f-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="7609f-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7609f-664">Índices</span><span class="sxs-lookup"><span data-stu-id="7609f-664">Indexes</span></span>  
  
|<span data-ttu-id="7609f-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="7609f-665">ColumnName</span></span>|<span data-ttu-id="7609f-666">DataType</span><span class="sxs-lookup"><span data-stu-id="7609f-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7609f-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-667">TABLE_CATALOG</span></span>|<span data-ttu-id="7609f-668">String</span><span class="sxs-lookup"><span data-stu-id="7609f-668">String</span></span>|  
|<span data-ttu-id="7609f-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="7609f-670">String</span><span class="sxs-lookup"><span data-stu-id="7609f-670">String</span></span>|  
|<span data-ttu-id="7609f-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-671">TABLE_NAME</span></span>|<span data-ttu-id="7609f-672">String</span><span class="sxs-lookup"><span data-stu-id="7609f-672">String</span></span>|  
|<span data-ttu-id="7609f-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7609f-673">INDEX_CATALOG</span></span>|<span data-ttu-id="7609f-674">String</span><span class="sxs-lookup"><span data-stu-id="7609f-674">String</span></span>|  
|<span data-ttu-id="7609f-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7609f-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="7609f-676">String</span><span class="sxs-lookup"><span data-stu-id="7609f-676">String</span></span>|  
|<span data-ttu-id="7609f-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-677">INDEX_NAME</span></span>|<span data-ttu-id="7609f-678">String</span><span class="sxs-lookup"><span data-stu-id="7609f-678">String</span></span>|  
|<span data-ttu-id="7609f-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7609f-679">PRIMARY_KEY</span></span>|<span data-ttu-id="7609f-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-680">Boolean</span></span>|  
|<span data-ttu-id="7609f-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7609f-681">UNIQUE</span></span>|<span data-ttu-id="7609f-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-682">Boolean</span></span>|  
|<span data-ttu-id="7609f-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7609f-683">CLUSTERED</span></span>|<span data-ttu-id="7609f-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-684">Boolean</span></span>|  
|<span data-ttu-id="7609f-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="7609f-685">TYPE</span></span>|<span data-ttu-id="7609f-686">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-686">Int32</span></span>|  
|<span data-ttu-id="7609f-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7609f-687">FILL_FACTOR</span></span>|<span data-ttu-id="7609f-688">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-688">Int32</span></span>|  
|<span data-ttu-id="7609f-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7609f-689">INITIAL_SIZE</span></span>|<span data-ttu-id="7609f-690">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-690">Int32</span></span>|  
|<span data-ttu-id="7609f-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="7609f-691">NULLS</span></span>|<span data-ttu-id="7609f-692">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-692">Int32</span></span>|  
|<span data-ttu-id="7609f-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7609f-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7609f-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-694">Boolean</span></span>|  
|<span data-ttu-id="7609f-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7609f-695">AUTO_UPDATE</span></span>|<span data-ttu-id="7609f-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="7609f-696">Boolean</span></span>|  
|<span data-ttu-id="7609f-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-697">NULL_COLLATION</span></span>|<span data-ttu-id="7609f-698">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-698">Int32</span></span>|  
|<span data-ttu-id="7609f-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7609f-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="7609f-700">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-700">Int64</span></span>|  
|<span data-ttu-id="7609f-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7609f-701">COLUMN_NAME</span></span>|<span data-ttu-id="7609f-702">String</span><span class="sxs-lookup"><span data-stu-id="7609f-702">String</span></span>|  
|<span data-ttu-id="7609f-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7609f-703">COLUMN_GUID</span></span>|<span data-ttu-id="7609f-704">Guid</span><span class="sxs-lookup"><span data-stu-id="7609f-704">Guid</span></span>|  
|<span data-ttu-id="7609f-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7609f-705">COLUMN_PROPID</span></span>|<span data-ttu-id="7609f-706">Int64</span><span class="sxs-lookup"><span data-stu-id="7609f-706">Int64</span></span>|  
|<span data-ttu-id="7609f-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7609f-707">COLLATION</span></span>|<span data-ttu-id="7609f-708">Int16</span><span class="sxs-lookup"><span data-stu-id="7609f-708">Int16</span></span>|  
|<span data-ttu-id="7609f-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7609f-709">CARDINALITY</span></span>|<span data-ttu-id="7609f-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="7609f-710">Decimal</span></span>|  
|<span data-ttu-id="7609f-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="7609f-711">PAGES</span></span>|<span data-ttu-id="7609f-712">Int32</span><span class="sxs-lookup"><span data-stu-id="7609f-712">Int32</span></span>|  
|<span data-ttu-id="7609f-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7609f-713">FILTER_CONDITION</span></span>|<span data-ttu-id="7609f-714">String</span><span class="sxs-lookup"><span data-stu-id="7609f-714">String</span></span>|  
|<span data-ttu-id="7609f-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7609f-715">INTEGRATED</span></span>|<span data-ttu-id="7609f-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="7609f-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7609f-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="7609f-717">See Also</span></span>  
 [<span data-ttu-id="7609f-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="7609f-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

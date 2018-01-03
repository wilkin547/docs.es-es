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
ms.workload: dotnet
ms.openlocfilehash: e120ea532b6da455e31ce7345b6c4b2be1ec975f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="fff5b-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="fff5b-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="fff5b-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="fff5b-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="fff5b-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="fff5b-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="fff5b-105">El controlador OLE DB de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="fff5b-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="fff5b-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="fff5b-106">Tables</span></span>  
  
-   <span data-ttu-id="fff5b-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="fff5b-107">Columns</span></span>  
  
-   <span data-ttu-id="fff5b-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fff5b-108">Procedures</span></span>  
  
-   <span data-ttu-id="fff5b-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fff5b-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="fff5b-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="fff5b-110">Catalog</span></span>  
  
-   <span data-ttu-id="fff5b-111">Índices</span><span class="sxs-lookup"><span data-stu-id="fff5b-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="fff5b-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="fff5b-112">Tables</span></span>  
  
|<span data-ttu-id="fff5b-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-113">ColumnName</span></span>|<span data-ttu-id="fff5b-114">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-115">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-116">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-116">String</span></span>|  
|<span data-ttu-id="fff5b-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-118">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-118">String</span></span>|  
|<span data-ttu-id="fff5b-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-119">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-120">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-120">String</span></span>|  
|<span data-ttu-id="fff5b-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-121">TABLE_TYPE</span></span>|<span data-ttu-id="fff5b-122">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-122">String</span></span>|  
|<span data-ttu-id="fff5b-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-123">TABLE_GUID</span></span>|<span data-ttu-id="fff5b-124">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-124">Guid</span></span>|  
|<span data-ttu-id="fff5b-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-125">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-126">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-126">String</span></span>|  
|<span data-ttu-id="fff5b-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-127">TABLE_PROPID</span></span>|<span data-ttu-id="fff5b-128">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-128">Int64</span></span>|  
|<span data-ttu-id="fff5b-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-129">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-130">DateTime</span></span>|  
|<span data-ttu-id="fff5b-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-131">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fff5b-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="fff5b-133">Columns</span></span>  
  
|<span data-ttu-id="fff5b-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-134">ColumnName</span></span>|<span data-ttu-id="fff5b-135">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-136">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-137">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-137">String</span></span>|  
|<span data-ttu-id="fff5b-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-139">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-139">String</span></span>|  
|<span data-ttu-id="fff5b-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-140">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-141">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-141">String</span></span>|  
|<span data-ttu-id="fff5b-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-142">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-143">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-143">String</span></span>|  
|<span data-ttu-id="fff5b-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-144">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-145">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-145">Guid</span></span>|  
|<span data-ttu-id="fff5b-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-146">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-147">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-147">Int64</span></span>|  
|<span data-ttu-id="fff5b-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-149">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-149">Int64</span></span>|  
|<span data-ttu-id="fff5b-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="fff5b-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-151">Boolean</span></span>|  
|<span data-ttu-id="fff5b-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="fff5b-153">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-153">String</span></span>|  
|<span data-ttu-id="fff5b-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fff5b-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="fff5b-155">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-155">Int64</span></span>|  
|<span data-ttu-id="fff5b-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-156">IS_NULLABLE</span></span>|<span data-ttu-id="fff5b-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-157">Boolean</span></span>|  
|<span data-ttu-id="fff5b-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-158">DATA_TYPE</span></span>|<span data-ttu-id="fff5b-159">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-159">Int32</span></span>|  
|<span data-ttu-id="fff5b-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-160">TYPE_GUID</span></span>|<span data-ttu-id="fff5b-161">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-161">Guid</span></span>|  
|<span data-ttu-id="fff5b-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fff5b-163">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-163">Int64</span></span>|  
|<span data-ttu-id="fff5b-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fff5b-165">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-165">Int64</span></span>|  
|<span data-ttu-id="fff5b-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fff5b-167">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-167">Int32</span></span>|  
|<span data-ttu-id="fff5b-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fff5b-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="fff5b-169">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-169">Int16</span></span>|  
|<span data-ttu-id="fff5b-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="fff5b-171">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-171">Int64</span></span>|  
|<span data-ttu-id="fff5b-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="fff5b-173">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-173">String</span></span>|  
|<span data-ttu-id="fff5b-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="fff5b-175">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-175">String</span></span>|  
|<span data-ttu-id="fff5b-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="fff5b-177">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-177">String</span></span>|  
|<span data-ttu-id="fff5b-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="fff5b-179">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-179">String</span></span>|  
|<span data-ttu-id="fff5b-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="fff5b-181">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-181">String</span></span>|  
|<span data-ttu-id="fff5b-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-182">COLLATION_NAME</span></span>|<span data-ttu-id="fff5b-183">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-183">String</span></span>|  
|<span data-ttu-id="fff5b-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="fff5b-185">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-185">String</span></span>|  
|<span data-ttu-id="fff5b-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="fff5b-187">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-187">String</span></span>|  
|<span data-ttu-id="fff5b-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-188">DOMAIN_NAME</span></span>|<span data-ttu-id="fff5b-189">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-189">String</span></span>|  
|<span data-ttu-id="fff5b-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-190">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-191">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-191">String</span></span>|  
|<span data-ttu-id="fff5b-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="fff5b-192">COLUMN_LCID</span></span>|<span data-ttu-id="fff5b-193">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-193">Int32</span></span>|  
|<span data-ttu-id="fff5b-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="fff5b-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="fff5b-195">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-195">Int32</span></span>|  
|<span data-ttu-id="fff5b-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="fff5b-196">COLUMN_SORTID</span></span>|<span data-ttu-id="fff5b-197">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-197">Int32</span></span>|  
|<span data-ttu-id="fff5b-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="fff5b-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="fff5b-199">Byte[]</span></span>|  
|<span data-ttu-id="fff5b-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="fff5b-200">IS_COMPUTED</span></span>|<span data-ttu-id="fff5b-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fff5b-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fff5b-202">Procedures</span></span>  
  
|<span data-ttu-id="fff5b-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-203">ColumnName</span></span>|<span data-ttu-id="fff5b-204">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fff5b-206">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-206">String</span></span>|  
|<span data-ttu-id="fff5b-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fff5b-208">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-208">String</span></span>|  
|<span data-ttu-id="fff5b-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="fff5b-210">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-210">String</span></span>|  
|<span data-ttu-id="fff5b-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fff5b-212">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-212">Int16</span></span>|  
|<span data-ttu-id="fff5b-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="fff5b-214">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-214">String</span></span>|  
|<span data-ttu-id="fff5b-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-215">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-216">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-216">String</span></span>|  
|<span data-ttu-id="fff5b-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-217">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-218">DateTime</span></span>|  
|<span data-ttu-id="fff5b-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-219">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="fff5b-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fff5b-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="fff5b-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-222">ColumnName</span></span>|<span data-ttu-id="fff5b-223">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fff5b-225">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-225">String</span></span>|  
|<span data-ttu-id="fff5b-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fff5b-227">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-227">String</span></span>|  
|<span data-ttu-id="fff5b-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="fff5b-229">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-229">String</span></span>|  
|<span data-ttu-id="fff5b-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-230">PARAMETER_NAME</span></span>|<span data-ttu-id="fff5b-231">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-231">String</span></span>|  
|<span data-ttu-id="fff5b-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-233">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-233">Int32</span></span>|  
|<span data-ttu-id="fff5b-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="fff5b-235">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-235">Int32</span></span>|  
|<span data-ttu-id="fff5b-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="fff5b-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-237">Boolean</span></span>|  
|<span data-ttu-id="fff5b-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="fff5b-239">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-239">String</span></span>|  
|<span data-ttu-id="fff5b-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-240">IS_NULLABLE</span></span>|<span data-ttu-id="fff5b-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-241">Boolean</span></span>|  
|<span data-ttu-id="fff5b-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-242">DATA_TYPE</span></span>|<span data-ttu-id="fff5b-243">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-243">Int32</span></span>|  
|<span data-ttu-id="fff5b-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fff5b-245">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-245">Int64</span></span>|  
|<span data-ttu-id="fff5b-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fff5b-247">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-247">Int64</span></span>|  
|<span data-ttu-id="fff5b-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fff5b-249">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-249">Int32</span></span>|  
|<span data-ttu-id="fff5b-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fff5b-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="fff5b-251">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-251">Int16</span></span>|  
|<span data-ttu-id="fff5b-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-252">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-253">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-253">String</span></span>|  
|<span data-ttu-id="fff5b-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-254">TYPE_NAME</span></span>|<span data-ttu-id="fff5b-255">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-255">String</span></span>|  
|<span data-ttu-id="fff5b-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="fff5b-257">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="fff5b-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="fff5b-258">Catalog</span></span>  
  
|<span data-ttu-id="fff5b-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-259">ColumnName</span></span>|<span data-ttu-id="fff5b-260">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-261">CATALOG_NAME</span></span>|<span data-ttu-id="fff5b-262">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-262">String</span></span>|  
|<span data-ttu-id="fff5b-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-263">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-264">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fff5b-265">Índices</span><span class="sxs-lookup"><span data-stu-id="fff5b-265">Indexes</span></span>  
  
|<span data-ttu-id="fff5b-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-266">ColumnName</span></span>|<span data-ttu-id="fff5b-267">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-268">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-269">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-269">String</span></span>|  
|<span data-ttu-id="fff5b-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-271">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-271">String</span></span>|  
|<span data-ttu-id="fff5b-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-272">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-273">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-273">String</span></span>|  
|<span data-ttu-id="fff5b-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-274">INDEX_CATALOG</span></span>|<span data-ttu-id="fff5b-275">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-275">String</span></span>|  
|<span data-ttu-id="fff5b-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="fff5b-277">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-277">String</span></span>|  
|<span data-ttu-id="fff5b-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-278">INDEX_NAME</span></span>|<span data-ttu-id="fff5b-279">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-279">String</span></span>|  
|<span data-ttu-id="fff5b-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="fff5b-280">PRIMARY_KEY</span></span>|<span data-ttu-id="fff5b-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-281">Boolean</span></span>|  
|<span data-ttu-id="fff5b-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fff5b-282">UNIQUE</span></span>|<span data-ttu-id="fff5b-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-283">Boolean</span></span>|  
|<span data-ttu-id="fff5b-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="fff5b-284">CLUSTERED</span></span>|<span data-ttu-id="fff5b-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-285">Boolean</span></span>|  
|<span data-ttu-id="fff5b-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-286">TYPE</span></span>|<span data-ttu-id="fff5b-287">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-287">Int32</span></span>|  
|<span data-ttu-id="fff5b-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="fff5b-288">FILL_FACTOR</span></span>|<span data-ttu-id="fff5b-289">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-289">Int32</span></span>|  
|<span data-ttu-id="fff5b-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="fff5b-290">INITIAL_SIZE</span></span>|<span data-ttu-id="fff5b-291">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-291">Int32</span></span>|  
|<span data-ttu-id="fff5b-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="fff5b-292">NULLS</span></span>|<span data-ttu-id="fff5b-293">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-293">Int32</span></span>|  
|<span data-ttu-id="fff5b-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="fff5b-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="fff5b-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-295">Boolean</span></span>|  
|<span data-ttu-id="fff5b-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="fff5b-296">AUTO_UPDATE</span></span>|<span data-ttu-id="fff5b-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-297">Boolean</span></span>|  
|<span data-ttu-id="fff5b-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-298">NULL_COLLATION</span></span>|<span data-ttu-id="fff5b-299">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-299">Int32</span></span>|  
|<span data-ttu-id="fff5b-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-301">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-301">Int64</span></span>|  
|<span data-ttu-id="fff5b-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-302">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-303">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-303">String</span></span>|  
|<span data-ttu-id="fff5b-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-304">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-305">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-305">Guid</span></span>|  
|<span data-ttu-id="fff5b-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-306">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-307">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-307">Int64</span></span>|  
|<span data-ttu-id="fff5b-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-308">COLLATION</span></span>|<span data-ttu-id="fff5b-309">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-309">Int16</span></span>|  
|<span data-ttu-id="fff5b-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fff5b-310">CARDINALITY</span></span>|<span data-ttu-id="fff5b-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="fff5b-311">Decimal</span></span>|  
|<span data-ttu-id="fff5b-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="fff5b-312">PAGES</span></span>|<span data-ttu-id="fff5b-313">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-313">Int32</span></span>|  
|<span data-ttu-id="fff5b-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-314">FILTER_CONDITION</span></span>|<span data-ttu-id="fff5b-315">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-315">String</span></span>|  
|<span data-ttu-id="fff5b-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-316">INTEGRATED</span></span>|<span data-ttu-id="fff5b-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="fff5b-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="fff5b-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="fff5b-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="fff5b-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="fff5b-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="fff5b-320">Tables</span></span>  
  
-   <span data-ttu-id="fff5b-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="fff5b-321">Columns</span></span>  
  
-   <span data-ttu-id="fff5b-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fff5b-322">Procedures</span></span>  
  
-   <span data-ttu-id="fff5b-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fff5b-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="fff5b-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="fff5b-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="fff5b-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="fff5b-325">Views</span></span>  
  
-   <span data-ttu-id="fff5b-326">Índices</span><span class="sxs-lookup"><span data-stu-id="fff5b-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="fff5b-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="fff5b-327">Tables</span></span>  
  
|<span data-ttu-id="fff5b-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-328">ColumnName</span></span>|<span data-ttu-id="fff5b-329">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-330">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-331">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-331">String</span></span>|  
|<span data-ttu-id="fff5b-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-333">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-333">String</span></span>|  
|<span data-ttu-id="fff5b-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-334">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-335">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-335">String</span></span>|  
|<span data-ttu-id="fff5b-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-336">TABLE_TYPE</span></span>|<span data-ttu-id="fff5b-337">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-337">String</span></span>|  
|<span data-ttu-id="fff5b-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-338">TABLE_GUID</span></span>|<span data-ttu-id="fff5b-339">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-339">Guid</span></span>|  
|<span data-ttu-id="fff5b-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-340">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-341">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-341">String</span></span>|  
|<span data-ttu-id="fff5b-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-342">TABLE_PROPID</span></span>|<span data-ttu-id="fff5b-343">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-343">Int64</span></span>|  
|<span data-ttu-id="fff5b-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-344">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-345">DateTime</span></span>|  
|<span data-ttu-id="fff5b-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-346">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fff5b-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="fff5b-348">Columns</span></span>  
  
|<span data-ttu-id="fff5b-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-349">ColumnName</span></span>|<span data-ttu-id="fff5b-350">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-351">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-352">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-352">String</span></span>|  
|<span data-ttu-id="fff5b-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-354">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-354">String</span></span>|  
|<span data-ttu-id="fff5b-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-355">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-356">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-356">String</span></span>|  
|<span data-ttu-id="fff5b-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-357">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-358">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-358">String</span></span>|  
|<span data-ttu-id="fff5b-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-359">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-360">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-360">Guid</span></span>|  
|<span data-ttu-id="fff5b-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-361">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-362">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-362">Int64</span></span>|  
|<span data-ttu-id="fff5b-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-364">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-364">Int64</span></span>|  
|<span data-ttu-id="fff5b-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="fff5b-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-366">Boolean</span></span>|  
|<span data-ttu-id="fff5b-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="fff5b-368">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-368">String</span></span>|  
|<span data-ttu-id="fff5b-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fff5b-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="fff5b-370">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-370">Int64</span></span>|  
|<span data-ttu-id="fff5b-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-371">IS_NULLABLE</span></span>|<span data-ttu-id="fff5b-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-372">Boolean</span></span>|  
|<span data-ttu-id="fff5b-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-373">DATA_TYPE</span></span>|<span data-ttu-id="fff5b-374">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-374">Int32</span></span>|  
|<span data-ttu-id="fff5b-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-375">TYPE_GUID</span></span>|<span data-ttu-id="fff5b-376">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-376">Guid</span></span>|  
|<span data-ttu-id="fff5b-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fff5b-378">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-378">Int64</span></span>|  
|<span data-ttu-id="fff5b-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fff5b-380">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-380">Int64</span></span>|  
|<span data-ttu-id="fff5b-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fff5b-382">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-382">Int32</span></span>|  
|<span data-ttu-id="fff5b-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fff5b-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="fff5b-384">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-384">Int16</span></span>|  
|<span data-ttu-id="fff5b-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="fff5b-386">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-386">Int64</span></span>|  
|<span data-ttu-id="fff5b-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="fff5b-388">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-388">String</span></span>|  
|<span data-ttu-id="fff5b-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="fff5b-390">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-390">String</span></span>|  
|<span data-ttu-id="fff5b-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="fff5b-392">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-392">String</span></span>|  
|<span data-ttu-id="fff5b-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="fff5b-394">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-394">String</span></span>|  
|<span data-ttu-id="fff5b-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="fff5b-396">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-396">String</span></span>|  
|<span data-ttu-id="fff5b-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-397">COLLATION_NAME</span></span>|<span data-ttu-id="fff5b-398">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-398">String</span></span>|  
|<span data-ttu-id="fff5b-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="fff5b-400">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-400">String</span></span>|  
|<span data-ttu-id="fff5b-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="fff5b-402">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-402">String</span></span>|  
|<span data-ttu-id="fff5b-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-403">DOMAIN_NAME</span></span>|<span data-ttu-id="fff5b-404">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-404">String</span></span>|  
|<span data-ttu-id="fff5b-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-405">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-406">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fff5b-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fff5b-407">Procedures</span></span>  
  
|<span data-ttu-id="fff5b-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-408">ColumnName</span></span>|<span data-ttu-id="fff5b-409">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fff5b-411">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-411">String</span></span>|  
|<span data-ttu-id="fff5b-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fff5b-413">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-413">String</span></span>|  
|<span data-ttu-id="fff5b-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="fff5b-415">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-415">String</span></span>|  
|<span data-ttu-id="fff5b-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fff5b-417">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-417">Int16</span></span>|  
|<span data-ttu-id="fff5b-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="fff5b-419">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-419">String</span></span>|  
|<span data-ttu-id="fff5b-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-420">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-421">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-421">String</span></span>|  
|<span data-ttu-id="fff5b-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-422">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-423">DateTime</span></span>|  
|<span data-ttu-id="fff5b-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-424">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="fff5b-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="fff5b-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="fff5b-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-427">ColumnName</span></span>|<span data-ttu-id="fff5b-428">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fff5b-430">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-430">String</span></span>|  
|<span data-ttu-id="fff5b-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fff5b-432">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-432">String</span></span>|  
|<span data-ttu-id="fff5b-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="fff5b-434">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-434">String</span></span>|  
|<span data-ttu-id="fff5b-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-435">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-436">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-436">String</span></span>|  
|<span data-ttu-id="fff5b-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-437">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-438">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-438">Guid</span></span>|  
|<span data-ttu-id="fff5b-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-439">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-440">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-440">Int64</span></span>|  
|<span data-ttu-id="fff5b-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="fff5b-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="fff5b-442">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-442">Int64</span></span>|  
|<span data-ttu-id="fff5b-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-444">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-444">Int64</span></span>|  
|<span data-ttu-id="fff5b-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-445">IS_NULLABLE</span></span>|<span data-ttu-id="fff5b-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-446">Boolean</span></span>|  
|<span data-ttu-id="fff5b-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-447">DATA_TYPE</span></span>|<span data-ttu-id="fff5b-448">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-448">Int32</span></span>|  
|<span data-ttu-id="fff5b-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-449">TYPE_GUID</span></span>|<span data-ttu-id="fff5b-450">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-450">Guid</span></span>|  
|<span data-ttu-id="fff5b-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fff5b-452">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-452">Int64</span></span>|  
|<span data-ttu-id="fff5b-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fff5b-454">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-454">Int64</span></span>|  
|<span data-ttu-id="fff5b-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fff5b-456">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-456">Int32</span></span>|  
|<span data-ttu-id="fff5b-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fff5b-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="fff5b-458">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-458">Int16</span></span>|  
|<span data-ttu-id="fff5b-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-459">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-460">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-460">String</span></span>|  
|<span data-ttu-id="fff5b-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="fff5b-461">OVERLOAD</span></span>|<span data-ttu-id="fff5b-462">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="fff5b-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="fff5b-463">Views</span></span>  
  
|<span data-ttu-id="fff5b-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-464">ColumnName</span></span>|<span data-ttu-id="fff5b-465">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-466">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-467">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-467">String</span></span>|  
|<span data-ttu-id="fff5b-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-469">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-469">String</span></span>|  
|<span data-ttu-id="fff5b-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-470">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-471">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-471">String</span></span>|  
|<span data-ttu-id="fff5b-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="fff5b-473">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-473">String</span></span>|  
|<span data-ttu-id="fff5b-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-474">CHECK_OPTION</span></span>|<span data-ttu-id="fff5b-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-475">Boolean</span></span>|  
|<span data-ttu-id="fff5b-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-476">IS_UPDATABLE</span></span>|<span data-ttu-id="fff5b-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-477">Boolean</span></span>|  
|<span data-ttu-id="fff5b-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-478">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-479">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-479">String</span></span>|  
|<span data-ttu-id="fff5b-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-480">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-481">DateTime</span></span>|  
|<span data-ttu-id="fff5b-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-482">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fff5b-484">Índices</span><span class="sxs-lookup"><span data-stu-id="fff5b-484">Indexes</span></span>  
  
|<span data-ttu-id="fff5b-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-485">ColumnName</span></span>|<span data-ttu-id="fff5b-486">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-487">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-488">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-488">String</span></span>|  
|<span data-ttu-id="fff5b-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-490">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-490">String</span></span>|  
|<span data-ttu-id="fff5b-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-491">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-492">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-492">String</span></span>|  
|<span data-ttu-id="fff5b-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-493">INDEX_CATALOG</span></span>|<span data-ttu-id="fff5b-494">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-494">String</span></span>|  
|<span data-ttu-id="fff5b-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="fff5b-496">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-496">String</span></span>|  
|<span data-ttu-id="fff5b-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-497">INDEX_NAME</span></span>|<span data-ttu-id="fff5b-498">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-498">String</span></span>|  
|<span data-ttu-id="fff5b-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="fff5b-499">PRIMARY_KEY</span></span>|<span data-ttu-id="fff5b-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-500">Boolean</span></span>|  
|<span data-ttu-id="fff5b-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fff5b-501">UNIQUE</span></span>|<span data-ttu-id="fff5b-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-502">Boolean</span></span>|  
|<span data-ttu-id="fff5b-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="fff5b-503">CLUSTERED</span></span>|<span data-ttu-id="fff5b-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-504">Boolean</span></span>|  
|<span data-ttu-id="fff5b-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-505">TYPE</span></span>|<span data-ttu-id="fff5b-506">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-506">Int32</span></span>|  
|<span data-ttu-id="fff5b-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="fff5b-507">FILL_FACTOR</span></span>|<span data-ttu-id="fff5b-508">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-508">Int32</span></span>|  
|<span data-ttu-id="fff5b-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="fff5b-509">INITIAL_SIZE</span></span>|<span data-ttu-id="fff5b-510">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-510">Int32</span></span>|  
|<span data-ttu-id="fff5b-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="fff5b-511">NULLS</span></span>|<span data-ttu-id="fff5b-512">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-512">Int32</span></span>|  
|<span data-ttu-id="fff5b-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="fff5b-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="fff5b-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-514">Boolean</span></span>|  
|<span data-ttu-id="fff5b-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="fff5b-515">AUTO_UPDATE</span></span>|<span data-ttu-id="fff5b-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-516">Boolean</span></span>|  
|<span data-ttu-id="fff5b-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-517">NULL_COLLATION</span></span>|<span data-ttu-id="fff5b-518">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-518">Int32</span></span>|  
|<span data-ttu-id="fff5b-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-520">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-520">Int64</span></span>|  
|<span data-ttu-id="fff5b-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-521">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-522">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-522">String</span></span>|  
|<span data-ttu-id="fff5b-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-523">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-524">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-524">Guid</span></span>|  
|<span data-ttu-id="fff5b-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-525">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-526">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-526">Int64</span></span>|  
|<span data-ttu-id="fff5b-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-527">COLLATION</span></span>|<span data-ttu-id="fff5b-528">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-528">Int16</span></span>|  
|<span data-ttu-id="fff5b-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fff5b-529">CARDINALITY</span></span>|<span data-ttu-id="fff5b-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="fff5b-530">Decimal</span></span>|  
|<span data-ttu-id="fff5b-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="fff5b-531">PAGES</span></span>|<span data-ttu-id="fff5b-532">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-532">Int32</span></span>|  
|<span data-ttu-id="fff5b-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-533">FILTER_CONDITION</span></span>|<span data-ttu-id="fff5b-534">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-534">String</span></span>|  
|<span data-ttu-id="fff5b-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-535">INTEGRATED</span></span>|<span data-ttu-id="fff5b-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="fff5b-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="fff5b-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="fff5b-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="fff5b-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="fff5b-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="fff5b-539">Tables</span></span>  
  
-   <span data-ttu-id="fff5b-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="fff5b-540">Columns</span></span>  
  
-   <span data-ttu-id="fff5b-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fff5b-541">Procedures</span></span>  
  
-   <span data-ttu-id="fff5b-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="fff5b-542">Views</span></span>  
  
-   <span data-ttu-id="fff5b-543">Índices</span><span class="sxs-lookup"><span data-stu-id="fff5b-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="fff5b-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="fff5b-544">Tables</span></span>  
  
|<span data-ttu-id="fff5b-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-545">ColumnName</span></span>|<span data-ttu-id="fff5b-546">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-547">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-548">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-548">String</span></span>|  
|<span data-ttu-id="fff5b-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-550">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-550">String</span></span>|  
|<span data-ttu-id="fff5b-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-551">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-552">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-552">String</span></span>|  
|<span data-ttu-id="fff5b-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-553">TABLE_TYPE</span></span>|<span data-ttu-id="fff5b-554">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-554">String</span></span>|  
|<span data-ttu-id="fff5b-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-555">TABLE_GUID</span></span>|<span data-ttu-id="fff5b-556">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-556">Guid</span></span>|  
|<span data-ttu-id="fff5b-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-557">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-558">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-558">String</span></span>|  
|<span data-ttu-id="fff5b-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-559">TABLE_PROPID</span></span>|<span data-ttu-id="fff5b-560">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-560">Int64</span></span>|  
|<span data-ttu-id="fff5b-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-561">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-562">DateTime</span></span>|  
|<span data-ttu-id="fff5b-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-563">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="fff5b-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="fff5b-565">Columns</span></span>  
  
|<span data-ttu-id="fff5b-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-566">ColumnName</span></span>|<span data-ttu-id="fff5b-567">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-568">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-569">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-569">String</span></span>|  
|<span data-ttu-id="fff5b-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-571">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-571">String</span></span>|  
|<span data-ttu-id="fff5b-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-572">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-573">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-573">String</span></span>|  
|<span data-ttu-id="fff5b-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-574">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-575">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-575">String</span></span>|  
|<span data-ttu-id="fff5b-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-576">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-577">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-577">Guid</span></span>|  
|<span data-ttu-id="fff5b-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-578">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-579">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-579">Int64</span></span>|  
|<span data-ttu-id="fff5b-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-581">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-581">Int64</span></span>|  
|<span data-ttu-id="fff5b-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="fff5b-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-583">Boolean</span></span>|  
|<span data-ttu-id="fff5b-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="fff5b-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="fff5b-585">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-585">String</span></span>|  
|<span data-ttu-id="fff5b-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fff5b-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="fff5b-587">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-587">Int64</span></span>|  
|<span data-ttu-id="fff5b-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-588">IS_NULLABLE</span></span>|<span data-ttu-id="fff5b-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-589">Boolean</span></span>|  
|<span data-ttu-id="fff5b-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-590">DATA_TYPE</span></span>|<span data-ttu-id="fff5b-591">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-591">Int32</span></span>|  
|<span data-ttu-id="fff5b-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-592">TYPE_GUID</span></span>|<span data-ttu-id="fff5b-593">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-593">Guid</span></span>|  
|<span data-ttu-id="fff5b-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="fff5b-595">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-595">Int64</span></span>|  
|<span data-ttu-id="fff5b-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="fff5b-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="fff5b-597">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-597">Int64</span></span>|  
|<span data-ttu-id="fff5b-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="fff5b-599">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-599">Int32</span></span>|  
|<span data-ttu-id="fff5b-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="fff5b-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="fff5b-601">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-601">Int16</span></span>|  
|<span data-ttu-id="fff5b-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="fff5b-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="fff5b-603">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-603">Int64</span></span>|  
|<span data-ttu-id="fff5b-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="fff5b-605">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-605">String</span></span>|  
|<span data-ttu-id="fff5b-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="fff5b-607">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-607">String</span></span>|  
|<span data-ttu-id="fff5b-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="fff5b-609">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-609">String</span></span>|  
|<span data-ttu-id="fff5b-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="fff5b-611">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-611">String</span></span>|  
|<span data-ttu-id="fff5b-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="fff5b-613">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-613">String</span></span>|  
|<span data-ttu-id="fff5b-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-614">COLLATION_NAME</span></span>|<span data-ttu-id="fff5b-615">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-615">String</span></span>|  
|<span data-ttu-id="fff5b-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="fff5b-617">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-617">String</span></span>|  
|<span data-ttu-id="fff5b-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="fff5b-619">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-619">String</span></span>|  
|<span data-ttu-id="fff5b-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-620">DOMAIN_NAME</span></span>|<span data-ttu-id="fff5b-621">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-621">String</span></span>|  
|<span data-ttu-id="fff5b-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-622">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-623">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="fff5b-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fff5b-624">Procedures</span></span>  
  
|<span data-ttu-id="fff5b-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-625">ColumnName</span></span>|<span data-ttu-id="fff5b-626">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="fff5b-628">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-628">String</span></span>|  
|<span data-ttu-id="fff5b-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="fff5b-630">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-630">String</span></span>|  
|<span data-ttu-id="fff5b-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="fff5b-632">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-632">String</span></span>|  
|<span data-ttu-id="fff5b-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="fff5b-634">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-634">Int16</span></span>|  
|<span data-ttu-id="fff5b-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="fff5b-636">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-636">String</span></span>|  
|<span data-ttu-id="fff5b-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-637">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-638">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-638">String</span></span>|  
|<span data-ttu-id="fff5b-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-639">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-640">DateTime</span></span>|  
|<span data-ttu-id="fff5b-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-641">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="fff5b-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="fff5b-643">Views</span></span>  
  
|<span data-ttu-id="fff5b-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-644">ColumnName</span></span>|<span data-ttu-id="fff5b-645">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-646">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-647">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-647">String</span></span>|  
|<span data-ttu-id="fff5b-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-649">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-649">String</span></span>|  
|<span data-ttu-id="fff5b-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-650">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-651">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-651">String</span></span>|  
|<span data-ttu-id="fff5b-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="fff5b-653">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-653">String</span></span>|  
|<span data-ttu-id="fff5b-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-654">CHECK_OPTION</span></span>|<span data-ttu-id="fff5b-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-655">Boolean</span></span>|  
|<span data-ttu-id="fff5b-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="fff5b-656">IS_UPDATABLE</span></span>|<span data-ttu-id="fff5b-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-657">Boolean</span></span>|  
|<span data-ttu-id="fff5b-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fff5b-658">DESCRIPTION</span></span>|<span data-ttu-id="fff5b-659">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-659">String</span></span>|  
|<span data-ttu-id="fff5b-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-660">DATE_CREATED</span></span>|<span data-ttu-id="fff5b-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-661">DateTime</span></span>|  
|<span data-ttu-id="fff5b-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="fff5b-662">DATE_MODIFIED</span></span>|<span data-ttu-id="fff5b-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="fff5b-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="fff5b-664">Índices</span><span class="sxs-lookup"><span data-stu-id="fff5b-664">Indexes</span></span>  
  
|<span data-ttu-id="fff5b-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="fff5b-665">ColumnName</span></span>|<span data-ttu-id="fff5b-666">DataType</span><span class="sxs-lookup"><span data-stu-id="fff5b-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="fff5b-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-667">TABLE_CATALOG</span></span>|<span data-ttu-id="fff5b-668">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-668">String</span></span>|  
|<span data-ttu-id="fff5b-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="fff5b-670">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-670">String</span></span>|  
|<span data-ttu-id="fff5b-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-671">TABLE_NAME</span></span>|<span data-ttu-id="fff5b-672">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-672">String</span></span>|  
|<span data-ttu-id="fff5b-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="fff5b-673">INDEX_CATALOG</span></span>|<span data-ttu-id="fff5b-674">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-674">String</span></span>|  
|<span data-ttu-id="fff5b-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="fff5b-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="fff5b-676">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-676">String</span></span>|  
|<span data-ttu-id="fff5b-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-677">INDEX_NAME</span></span>|<span data-ttu-id="fff5b-678">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-678">String</span></span>|  
|<span data-ttu-id="fff5b-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="fff5b-679">PRIMARY_KEY</span></span>|<span data-ttu-id="fff5b-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-680">Boolean</span></span>|  
|<span data-ttu-id="fff5b-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="fff5b-681">UNIQUE</span></span>|<span data-ttu-id="fff5b-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-682">Boolean</span></span>|  
|<span data-ttu-id="fff5b-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="fff5b-683">CLUSTERED</span></span>|<span data-ttu-id="fff5b-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-684">Boolean</span></span>|  
|<span data-ttu-id="fff5b-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="fff5b-685">TYPE</span></span>|<span data-ttu-id="fff5b-686">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-686">Int32</span></span>|  
|<span data-ttu-id="fff5b-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="fff5b-687">FILL_FACTOR</span></span>|<span data-ttu-id="fff5b-688">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-688">Int32</span></span>|  
|<span data-ttu-id="fff5b-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="fff5b-689">INITIAL_SIZE</span></span>|<span data-ttu-id="fff5b-690">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-690">Int32</span></span>|  
|<span data-ttu-id="fff5b-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="fff5b-691">NULLS</span></span>|<span data-ttu-id="fff5b-692">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-692">Int32</span></span>|  
|<span data-ttu-id="fff5b-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="fff5b-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="fff5b-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-694">Boolean</span></span>|  
|<span data-ttu-id="fff5b-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="fff5b-695">AUTO_UPDATE</span></span>|<span data-ttu-id="fff5b-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="fff5b-696">Boolean</span></span>|  
|<span data-ttu-id="fff5b-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-697">NULL_COLLATION</span></span>|<span data-ttu-id="fff5b-698">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-698">Int32</span></span>|  
|<span data-ttu-id="fff5b-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="fff5b-700">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-700">Int64</span></span>|  
|<span data-ttu-id="fff5b-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="fff5b-701">COLUMN_NAME</span></span>|<span data-ttu-id="fff5b-702">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-702">String</span></span>|  
|<span data-ttu-id="fff5b-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="fff5b-703">COLUMN_GUID</span></span>|<span data-ttu-id="fff5b-704">Guid</span><span class="sxs-lookup"><span data-stu-id="fff5b-704">Guid</span></span>|  
|<span data-ttu-id="fff5b-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="fff5b-705">COLUMN_PROPID</span></span>|<span data-ttu-id="fff5b-706">Int64</span><span class="sxs-lookup"><span data-stu-id="fff5b-706">Int64</span></span>|  
|<span data-ttu-id="fff5b-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="fff5b-707">COLLATION</span></span>|<span data-ttu-id="fff5b-708">Int16</span><span class="sxs-lookup"><span data-stu-id="fff5b-708">Int16</span></span>|  
|<span data-ttu-id="fff5b-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="fff5b-709">CARDINALITY</span></span>|<span data-ttu-id="fff5b-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="fff5b-710">Decimal</span></span>|  
|<span data-ttu-id="fff5b-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="fff5b-711">PAGES</span></span>|<span data-ttu-id="fff5b-712">Int32</span><span class="sxs-lookup"><span data-stu-id="fff5b-712">Int32</span></span>|  
|<span data-ttu-id="fff5b-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="fff5b-713">FILTER_CONDITION</span></span>|<span data-ttu-id="fff5b-714">String</span><span class="sxs-lookup"><span data-stu-id="fff5b-714">String</span></span>|  
|<span data-ttu-id="fff5b-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="fff5b-715">INTEGRATED</span></span>|<span data-ttu-id="fff5b-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="fff5b-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fff5b-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="fff5b-717">See Also</span></span>  
 [<span data-ttu-id="fff5b-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="fff5b-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645897"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="2fd74-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="2fd74-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="2fd74-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="2fd74-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="2fd74-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fd74-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="2fd74-105">El controlador OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="2fd74-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="2fd74-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="2fd74-106">Tables</span></span>  
  
- <span data-ttu-id="2fd74-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="2fd74-107">Columns</span></span>  
  
- <span data-ttu-id="2fd74-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2fd74-108">Procedures</span></span>  
  
- <span data-ttu-id="2fd74-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2fd74-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="2fd74-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="2fd74-110">Catalog</span></span>  
  
- <span data-ttu-id="2fd74-111">Índices</span><span class="sxs-lookup"><span data-stu-id="2fd74-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2fd74-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="2fd74-112">Tables</span></span>  
  
|<span data-ttu-id="2fd74-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-113">ColumnName</span></span>|<span data-ttu-id="2fd74-114">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-115">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-116">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-116">String</span></span>|  
|<span data-ttu-id="2fd74-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-118">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-118">String</span></span>|  
|<span data-ttu-id="2fd74-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-119">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-120">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-120">String</span></span>|  
|<span data-ttu-id="2fd74-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-121">TABLE_TYPE</span></span>|<span data-ttu-id="2fd74-122">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-122">String</span></span>|  
|<span data-ttu-id="2fd74-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-123">TABLE_GUID</span></span>|<span data-ttu-id="2fd74-124">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-124">Guid</span></span>|  
|<span data-ttu-id="2fd74-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-125">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-126">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-126">String</span></span>|  
|<span data-ttu-id="2fd74-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-127">TABLE_PROPID</span></span>|<span data-ttu-id="2fd74-128">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-128">Int64</span></span>|  
|<span data-ttu-id="2fd74-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-129">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-130">DateTime</span></span>|  
|<span data-ttu-id="2fd74-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-131">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2fd74-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="2fd74-133">Columns</span></span>  
  
|<span data-ttu-id="2fd74-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-134">ColumnName</span></span>|<span data-ttu-id="2fd74-135">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-136">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-137">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-137">String</span></span>|  
|<span data-ttu-id="2fd74-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-139">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-139">String</span></span>|  
|<span data-ttu-id="2fd74-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-140">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-141">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-141">String</span></span>|  
|<span data-ttu-id="2fd74-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-142">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-143">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-143">String</span></span>|  
|<span data-ttu-id="2fd74-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-144">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-145">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-145">Guid</span></span>|  
|<span data-ttu-id="2fd74-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-146">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-147">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-147">Int64</span></span>|  
|<span data-ttu-id="2fd74-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-149">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-149">Int64</span></span>|  
|<span data-ttu-id="2fd74-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2fd74-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-151">Boolean</span></span>|  
|<span data-ttu-id="2fd74-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2fd74-153">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-153">String</span></span>|  
|<span data-ttu-id="2fd74-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2fd74-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="2fd74-155">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-155">Int64</span></span>|  
|<span data-ttu-id="2fd74-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-156">IS_NULLABLE</span></span>|<span data-ttu-id="2fd74-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-157">Boolean</span></span>|  
|<span data-ttu-id="2fd74-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-158">DATA_TYPE</span></span>|<span data-ttu-id="2fd74-159">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-159">Int32</span></span>|  
|<span data-ttu-id="2fd74-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-160">TYPE_GUID</span></span>|<span data-ttu-id="2fd74-161">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-161">Guid</span></span>|  
|<span data-ttu-id="2fd74-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2fd74-163">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-163">Int64</span></span>|  
|<span data-ttu-id="2fd74-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2fd74-165">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-165">Int64</span></span>|  
|<span data-ttu-id="2fd74-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2fd74-167">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-167">Int32</span></span>|  
|<span data-ttu-id="2fd74-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2fd74-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="2fd74-169">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-169">Int16</span></span>|  
|<span data-ttu-id="2fd74-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="2fd74-171">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-171">Int64</span></span>|  
|<span data-ttu-id="2fd74-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2fd74-173">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-173">String</span></span>|  
|<span data-ttu-id="2fd74-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2fd74-175">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-175">String</span></span>|  
|<span data-ttu-id="2fd74-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2fd74-177">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-177">String</span></span>|  
|<span data-ttu-id="2fd74-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="2fd74-179">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-179">String</span></span>|  
|<span data-ttu-id="2fd74-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2fd74-181">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-181">String</span></span>|  
|<span data-ttu-id="2fd74-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-182">COLLATION_NAME</span></span>|<span data-ttu-id="2fd74-183">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-183">String</span></span>|  
|<span data-ttu-id="2fd74-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2fd74-185">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-185">String</span></span>|  
|<span data-ttu-id="2fd74-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2fd74-187">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-187">String</span></span>|  
|<span data-ttu-id="2fd74-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-188">DOMAIN_NAME</span></span>|<span data-ttu-id="2fd74-189">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-189">String</span></span>|  
|<span data-ttu-id="2fd74-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-190">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-191">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-191">String</span></span>|  
|<span data-ttu-id="2fd74-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="2fd74-192">COLUMN_LCID</span></span>|<span data-ttu-id="2fd74-193">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-193">Int32</span></span>|  
|<span data-ttu-id="2fd74-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="2fd74-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="2fd74-195">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-195">Int32</span></span>|  
|<span data-ttu-id="2fd74-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="2fd74-196">COLUMN_SORTID</span></span>|<span data-ttu-id="2fd74-197">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-197">Int32</span></span>|  
|<span data-ttu-id="2fd74-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="2fd74-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="2fd74-199">Byte[]</span></span>|  
|<span data-ttu-id="2fd74-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="2fd74-200">IS_COMPUTED</span></span>|<span data-ttu-id="2fd74-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2fd74-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2fd74-202">Procedures</span></span>  
  
|<span data-ttu-id="2fd74-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-203">ColumnName</span></span>|<span data-ttu-id="2fd74-204">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2fd74-206">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-206">String</span></span>|  
|<span data-ttu-id="2fd74-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2fd74-208">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-208">String</span></span>|  
|<span data-ttu-id="2fd74-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="2fd74-210">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-210">String</span></span>|  
|<span data-ttu-id="2fd74-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2fd74-212">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-212">Int16</span></span>|  
|<span data-ttu-id="2fd74-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2fd74-214">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-214">String</span></span>|  
|<span data-ttu-id="2fd74-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-215">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-216">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-216">String</span></span>|  
|<span data-ttu-id="2fd74-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-217">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-218">DateTime</span></span>|  
|<span data-ttu-id="2fd74-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-219">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="2fd74-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2fd74-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="2fd74-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-222">ColumnName</span></span>|<span data-ttu-id="2fd74-223">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2fd74-225">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-225">String</span></span>|  
|<span data-ttu-id="2fd74-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2fd74-227">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-227">String</span></span>|  
|<span data-ttu-id="2fd74-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="2fd74-229">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-229">String</span></span>|  
|<span data-ttu-id="2fd74-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-230">PARAMETER_NAME</span></span>|<span data-ttu-id="2fd74-231">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-231">String</span></span>|  
|<span data-ttu-id="2fd74-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-233">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-233">Int32</span></span>|  
|<span data-ttu-id="2fd74-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="2fd74-235">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-235">Int32</span></span>|  
|<span data-ttu-id="2fd74-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="2fd74-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-237">Boolean</span></span>|  
|<span data-ttu-id="2fd74-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="2fd74-239">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-239">String</span></span>|  
|<span data-ttu-id="2fd74-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-240">IS_NULLABLE</span></span>|<span data-ttu-id="2fd74-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-241">Boolean</span></span>|  
|<span data-ttu-id="2fd74-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-242">DATA_TYPE</span></span>|<span data-ttu-id="2fd74-243">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-243">Int32</span></span>|  
|<span data-ttu-id="2fd74-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2fd74-245">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-245">Int64</span></span>|  
|<span data-ttu-id="2fd74-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2fd74-247">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-247">Int64</span></span>|  
|<span data-ttu-id="2fd74-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2fd74-249">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-249">Int32</span></span>|  
|<span data-ttu-id="2fd74-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2fd74-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="2fd74-251">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-251">Int16</span></span>|  
|<span data-ttu-id="2fd74-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-252">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-253">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-253">String</span></span>|  
|<span data-ttu-id="2fd74-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-254">TYPE_NAME</span></span>|<span data-ttu-id="2fd74-255">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-255">String</span></span>|  
|<span data-ttu-id="2fd74-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="2fd74-257">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="2fd74-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="2fd74-258">Catalog</span></span>  
  
|<span data-ttu-id="2fd74-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-259">ColumnName</span></span>|<span data-ttu-id="2fd74-260">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-261">CATALOG_NAME</span></span>|<span data-ttu-id="2fd74-262">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-262">String</span></span>|  
|<span data-ttu-id="2fd74-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-263">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-264">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2fd74-265">Índices</span><span class="sxs-lookup"><span data-stu-id="2fd74-265">Indexes</span></span>  
  
|<span data-ttu-id="2fd74-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-266">ColumnName</span></span>|<span data-ttu-id="2fd74-267">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-268">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-269">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-269">String</span></span>|  
|<span data-ttu-id="2fd74-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-271">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-271">String</span></span>|  
|<span data-ttu-id="2fd74-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-272">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-273">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-273">String</span></span>|  
|<span data-ttu-id="2fd74-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-274">INDEX_CATALOG</span></span>|<span data-ttu-id="2fd74-275">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-275">String</span></span>|  
|<span data-ttu-id="2fd74-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="2fd74-277">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-277">String</span></span>|  
|<span data-ttu-id="2fd74-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-278">INDEX_NAME</span></span>|<span data-ttu-id="2fd74-279">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-279">String</span></span>|  
|<span data-ttu-id="2fd74-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2fd74-280">PRIMARY_KEY</span></span>|<span data-ttu-id="2fd74-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-281">Boolean</span></span>|  
|<span data-ttu-id="2fd74-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2fd74-282">UNIQUE</span></span>|<span data-ttu-id="2fd74-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-283">Boolean</span></span>|  
|<span data-ttu-id="2fd74-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2fd74-284">CLUSTERED</span></span>|<span data-ttu-id="2fd74-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-285">Boolean</span></span>|  
|<span data-ttu-id="2fd74-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-286">TYPE</span></span>|<span data-ttu-id="2fd74-287">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-287">Int32</span></span>|  
|<span data-ttu-id="2fd74-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2fd74-288">FILL_FACTOR</span></span>|<span data-ttu-id="2fd74-289">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-289">Int32</span></span>|  
|<span data-ttu-id="2fd74-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2fd74-290">INITIAL_SIZE</span></span>|<span data-ttu-id="2fd74-291">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-291">Int32</span></span>|  
|<span data-ttu-id="2fd74-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="2fd74-292">NULLS</span></span>|<span data-ttu-id="2fd74-293">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-293">Int32</span></span>|  
|<span data-ttu-id="2fd74-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2fd74-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2fd74-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-295">Boolean</span></span>|  
|<span data-ttu-id="2fd74-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2fd74-296">AUTO_UPDATE</span></span>|<span data-ttu-id="2fd74-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-297">Boolean</span></span>|  
|<span data-ttu-id="2fd74-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-298">NULL_COLLATION</span></span>|<span data-ttu-id="2fd74-299">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-299">Int32</span></span>|  
|<span data-ttu-id="2fd74-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-301">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-301">Int64</span></span>|  
|<span data-ttu-id="2fd74-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-302">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-303">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-303">String</span></span>|  
|<span data-ttu-id="2fd74-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-304">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-305">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-305">Guid</span></span>|  
|<span data-ttu-id="2fd74-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-306">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-307">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-307">Int64</span></span>|  
|<span data-ttu-id="2fd74-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-308">COLLATION</span></span>|<span data-ttu-id="2fd74-309">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-309">Int16</span></span>|  
|<span data-ttu-id="2fd74-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2fd74-310">CARDINALITY</span></span>|<span data-ttu-id="2fd74-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="2fd74-311">Decimal</span></span>|  
|<span data-ttu-id="2fd74-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="2fd74-312">PAGES</span></span>|<span data-ttu-id="2fd74-313">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-313">Int32</span></span>|  
|<span data-ttu-id="2fd74-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-314">FILTER_CONDITION</span></span>|<span data-ttu-id="2fd74-315">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-315">String</span></span>|  
|<span data-ttu-id="2fd74-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-316">INTEGRATED</span></span>|<span data-ttu-id="2fd74-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="2fd74-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="2fd74-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="2fd74-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="2fd74-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="2fd74-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="2fd74-320">Tables</span></span>  
  
- <span data-ttu-id="2fd74-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="2fd74-321">Columns</span></span>  
  
- <span data-ttu-id="2fd74-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2fd74-322">Procedures</span></span>  
  
- <span data-ttu-id="2fd74-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2fd74-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="2fd74-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2fd74-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="2fd74-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="2fd74-325">Views</span></span>  
  
- <span data-ttu-id="2fd74-326">Índices</span><span class="sxs-lookup"><span data-stu-id="2fd74-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2fd74-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="2fd74-327">Tables</span></span>  
  
|<span data-ttu-id="2fd74-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-328">ColumnName</span></span>|<span data-ttu-id="2fd74-329">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-330">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-331">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-331">String</span></span>|  
|<span data-ttu-id="2fd74-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-333">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-333">String</span></span>|  
|<span data-ttu-id="2fd74-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-334">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-335">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-335">String</span></span>|  
|<span data-ttu-id="2fd74-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-336">TABLE_TYPE</span></span>|<span data-ttu-id="2fd74-337">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-337">String</span></span>|  
|<span data-ttu-id="2fd74-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-338">TABLE_GUID</span></span>|<span data-ttu-id="2fd74-339">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-339">Guid</span></span>|  
|<span data-ttu-id="2fd74-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-340">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-341">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-341">String</span></span>|  
|<span data-ttu-id="2fd74-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-342">TABLE_PROPID</span></span>|<span data-ttu-id="2fd74-343">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-343">Int64</span></span>|  
|<span data-ttu-id="2fd74-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-344">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-345">DateTime</span></span>|  
|<span data-ttu-id="2fd74-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-346">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2fd74-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="2fd74-348">Columns</span></span>  
  
|<span data-ttu-id="2fd74-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-349">ColumnName</span></span>|<span data-ttu-id="2fd74-350">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-351">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-352">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-352">String</span></span>|  
|<span data-ttu-id="2fd74-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-354">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-354">String</span></span>|  
|<span data-ttu-id="2fd74-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-355">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-356">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-356">String</span></span>|  
|<span data-ttu-id="2fd74-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-357">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-358">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-358">String</span></span>|  
|<span data-ttu-id="2fd74-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-359">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-360">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-360">Guid</span></span>|  
|<span data-ttu-id="2fd74-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-361">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-362">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-362">Int64</span></span>|  
|<span data-ttu-id="2fd74-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-364">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-364">Int64</span></span>|  
|<span data-ttu-id="2fd74-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2fd74-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-366">Boolean</span></span>|  
|<span data-ttu-id="2fd74-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2fd74-368">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-368">String</span></span>|  
|<span data-ttu-id="2fd74-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2fd74-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="2fd74-370">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-370">Int64</span></span>|  
|<span data-ttu-id="2fd74-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-371">IS_NULLABLE</span></span>|<span data-ttu-id="2fd74-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-372">Boolean</span></span>|  
|<span data-ttu-id="2fd74-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-373">DATA_TYPE</span></span>|<span data-ttu-id="2fd74-374">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-374">Int32</span></span>|  
|<span data-ttu-id="2fd74-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-375">TYPE_GUID</span></span>|<span data-ttu-id="2fd74-376">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-376">Guid</span></span>|  
|<span data-ttu-id="2fd74-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2fd74-378">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-378">Int64</span></span>|  
|<span data-ttu-id="2fd74-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2fd74-380">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-380">Int64</span></span>|  
|<span data-ttu-id="2fd74-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2fd74-382">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-382">Int32</span></span>|  
|<span data-ttu-id="2fd74-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2fd74-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="2fd74-384">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-384">Int16</span></span>|  
|<span data-ttu-id="2fd74-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="2fd74-386">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-386">Int64</span></span>|  
|<span data-ttu-id="2fd74-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2fd74-388">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-388">String</span></span>|  
|<span data-ttu-id="2fd74-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2fd74-390">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-390">String</span></span>|  
|<span data-ttu-id="2fd74-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2fd74-392">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-392">String</span></span>|  
|<span data-ttu-id="2fd74-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="2fd74-394">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-394">String</span></span>|  
|<span data-ttu-id="2fd74-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2fd74-396">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-396">String</span></span>|  
|<span data-ttu-id="2fd74-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-397">COLLATION_NAME</span></span>|<span data-ttu-id="2fd74-398">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-398">String</span></span>|  
|<span data-ttu-id="2fd74-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2fd74-400">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-400">String</span></span>|  
|<span data-ttu-id="2fd74-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2fd74-402">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-402">String</span></span>|  
|<span data-ttu-id="2fd74-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-403">DOMAIN_NAME</span></span>|<span data-ttu-id="2fd74-404">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-404">String</span></span>|  
|<span data-ttu-id="2fd74-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-405">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-406">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2fd74-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2fd74-407">Procedures</span></span>  
  
|<span data-ttu-id="2fd74-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-408">ColumnName</span></span>|<span data-ttu-id="2fd74-409">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2fd74-411">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-411">String</span></span>|  
|<span data-ttu-id="2fd74-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2fd74-413">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-413">String</span></span>|  
|<span data-ttu-id="2fd74-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="2fd74-415">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-415">String</span></span>|  
|<span data-ttu-id="2fd74-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2fd74-417">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-417">Int16</span></span>|  
|<span data-ttu-id="2fd74-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2fd74-419">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-419">String</span></span>|  
|<span data-ttu-id="2fd74-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-420">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-421">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-421">String</span></span>|  
|<span data-ttu-id="2fd74-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-422">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-423">DateTime</span></span>|  
|<span data-ttu-id="2fd74-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-424">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="2fd74-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2fd74-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="2fd74-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-427">ColumnName</span></span>|<span data-ttu-id="2fd74-428">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2fd74-430">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-430">String</span></span>|  
|<span data-ttu-id="2fd74-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2fd74-432">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-432">String</span></span>|  
|<span data-ttu-id="2fd74-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="2fd74-434">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-434">String</span></span>|  
|<span data-ttu-id="2fd74-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-435">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-436">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-436">String</span></span>|  
|<span data-ttu-id="2fd74-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-437">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-438">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-438">Guid</span></span>|  
|<span data-ttu-id="2fd74-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-439">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-440">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-440">Int64</span></span>|  
|<span data-ttu-id="2fd74-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="2fd74-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="2fd74-442">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-442">Int64</span></span>|  
|<span data-ttu-id="2fd74-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-444">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-444">Int64</span></span>|  
|<span data-ttu-id="2fd74-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-445">IS_NULLABLE</span></span>|<span data-ttu-id="2fd74-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-446">Boolean</span></span>|  
|<span data-ttu-id="2fd74-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-447">DATA_TYPE</span></span>|<span data-ttu-id="2fd74-448">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-448">Int32</span></span>|  
|<span data-ttu-id="2fd74-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-449">TYPE_GUID</span></span>|<span data-ttu-id="2fd74-450">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-450">Guid</span></span>|  
|<span data-ttu-id="2fd74-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2fd74-452">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-452">Int64</span></span>|  
|<span data-ttu-id="2fd74-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2fd74-454">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-454">Int64</span></span>|  
|<span data-ttu-id="2fd74-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2fd74-456">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-456">Int32</span></span>|  
|<span data-ttu-id="2fd74-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2fd74-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="2fd74-458">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-458">Int16</span></span>|  
|<span data-ttu-id="2fd74-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-459">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-460">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-460">String</span></span>|  
|<span data-ttu-id="2fd74-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="2fd74-461">OVERLOAD</span></span>|<span data-ttu-id="2fd74-462">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2fd74-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="2fd74-463">Views</span></span>  
  
|<span data-ttu-id="2fd74-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-464">ColumnName</span></span>|<span data-ttu-id="2fd74-465">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-466">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-467">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-467">String</span></span>|  
|<span data-ttu-id="2fd74-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-469">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-469">String</span></span>|  
|<span data-ttu-id="2fd74-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-470">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-471">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-471">String</span></span>|  
|<span data-ttu-id="2fd74-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="2fd74-473">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-473">String</span></span>|  
|<span data-ttu-id="2fd74-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-474">CHECK_OPTION</span></span>|<span data-ttu-id="2fd74-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-475">Boolean</span></span>|  
|<span data-ttu-id="2fd74-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-476">IS_UPDATABLE</span></span>|<span data-ttu-id="2fd74-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-477">Boolean</span></span>|  
|<span data-ttu-id="2fd74-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-478">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-479">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-479">String</span></span>|  
|<span data-ttu-id="2fd74-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-480">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-481">DateTime</span></span>|  
|<span data-ttu-id="2fd74-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-482">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2fd74-484">Índices</span><span class="sxs-lookup"><span data-stu-id="2fd74-484">Indexes</span></span>  
  
|<span data-ttu-id="2fd74-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-485">ColumnName</span></span>|<span data-ttu-id="2fd74-486">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-487">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-488">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-488">String</span></span>|  
|<span data-ttu-id="2fd74-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-490">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-490">String</span></span>|  
|<span data-ttu-id="2fd74-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-491">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-492">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-492">String</span></span>|  
|<span data-ttu-id="2fd74-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-493">INDEX_CATALOG</span></span>|<span data-ttu-id="2fd74-494">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-494">String</span></span>|  
|<span data-ttu-id="2fd74-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="2fd74-496">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-496">String</span></span>|  
|<span data-ttu-id="2fd74-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-497">INDEX_NAME</span></span>|<span data-ttu-id="2fd74-498">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-498">String</span></span>|  
|<span data-ttu-id="2fd74-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2fd74-499">PRIMARY_KEY</span></span>|<span data-ttu-id="2fd74-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-500">Boolean</span></span>|  
|<span data-ttu-id="2fd74-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2fd74-501">UNIQUE</span></span>|<span data-ttu-id="2fd74-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-502">Boolean</span></span>|  
|<span data-ttu-id="2fd74-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2fd74-503">CLUSTERED</span></span>|<span data-ttu-id="2fd74-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-504">Boolean</span></span>|  
|<span data-ttu-id="2fd74-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-505">TYPE</span></span>|<span data-ttu-id="2fd74-506">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-506">Int32</span></span>|  
|<span data-ttu-id="2fd74-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2fd74-507">FILL_FACTOR</span></span>|<span data-ttu-id="2fd74-508">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-508">Int32</span></span>|  
|<span data-ttu-id="2fd74-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2fd74-509">INITIAL_SIZE</span></span>|<span data-ttu-id="2fd74-510">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-510">Int32</span></span>|  
|<span data-ttu-id="2fd74-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="2fd74-511">NULLS</span></span>|<span data-ttu-id="2fd74-512">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-512">Int32</span></span>|  
|<span data-ttu-id="2fd74-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2fd74-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2fd74-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-514">Boolean</span></span>|  
|<span data-ttu-id="2fd74-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2fd74-515">AUTO_UPDATE</span></span>|<span data-ttu-id="2fd74-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-516">Boolean</span></span>|  
|<span data-ttu-id="2fd74-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-517">NULL_COLLATION</span></span>|<span data-ttu-id="2fd74-518">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-518">Int32</span></span>|  
|<span data-ttu-id="2fd74-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-520">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-520">Int64</span></span>|  
|<span data-ttu-id="2fd74-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-521">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-522">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-522">String</span></span>|  
|<span data-ttu-id="2fd74-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-523">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-524">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-524">Guid</span></span>|  
|<span data-ttu-id="2fd74-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-525">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-526">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-526">Int64</span></span>|  
|<span data-ttu-id="2fd74-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-527">COLLATION</span></span>|<span data-ttu-id="2fd74-528">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-528">Int16</span></span>|  
|<span data-ttu-id="2fd74-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2fd74-529">CARDINALITY</span></span>|<span data-ttu-id="2fd74-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="2fd74-530">Decimal</span></span>|  
|<span data-ttu-id="2fd74-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="2fd74-531">PAGES</span></span>|<span data-ttu-id="2fd74-532">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-532">Int32</span></span>|  
|<span data-ttu-id="2fd74-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-533">FILTER_CONDITION</span></span>|<span data-ttu-id="2fd74-534">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-534">String</span></span>|  
|<span data-ttu-id="2fd74-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-535">INTEGRATED</span></span>|<span data-ttu-id="2fd74-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="2fd74-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="2fd74-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="2fd74-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="2fd74-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="2fd74-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="2fd74-539">Tables</span></span>  
  
- <span data-ttu-id="2fd74-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="2fd74-540">Columns</span></span>  
  
- <span data-ttu-id="2fd74-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2fd74-541">Procedures</span></span>  
  
- <span data-ttu-id="2fd74-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="2fd74-542">Views</span></span>  
  
- <span data-ttu-id="2fd74-543">Índices</span><span class="sxs-lookup"><span data-stu-id="2fd74-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="2fd74-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="2fd74-544">Tables</span></span>  
  
|<span data-ttu-id="2fd74-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-545">ColumnName</span></span>|<span data-ttu-id="2fd74-546">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-547">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-548">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-548">String</span></span>|  
|<span data-ttu-id="2fd74-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-550">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-550">String</span></span>|  
|<span data-ttu-id="2fd74-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-551">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-552">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-552">String</span></span>|  
|<span data-ttu-id="2fd74-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-553">TABLE_TYPE</span></span>|<span data-ttu-id="2fd74-554">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-554">String</span></span>|  
|<span data-ttu-id="2fd74-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-555">TABLE_GUID</span></span>|<span data-ttu-id="2fd74-556">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-556">Guid</span></span>|  
|<span data-ttu-id="2fd74-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-557">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-558">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-558">String</span></span>|  
|<span data-ttu-id="2fd74-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-559">TABLE_PROPID</span></span>|<span data-ttu-id="2fd74-560">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-560">Int64</span></span>|  
|<span data-ttu-id="2fd74-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-561">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-562">DateTime</span></span>|  
|<span data-ttu-id="2fd74-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-563">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="2fd74-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="2fd74-565">Columns</span></span>  
  
|<span data-ttu-id="2fd74-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-566">ColumnName</span></span>|<span data-ttu-id="2fd74-567">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-568">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-569">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-569">String</span></span>|  
|<span data-ttu-id="2fd74-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-571">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-571">String</span></span>|  
|<span data-ttu-id="2fd74-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-572">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-573">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-573">String</span></span>|  
|<span data-ttu-id="2fd74-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-574">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-575">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-575">String</span></span>|  
|<span data-ttu-id="2fd74-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-576">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-577">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-577">Guid</span></span>|  
|<span data-ttu-id="2fd74-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-578">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-579">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-579">Int64</span></span>|  
|<span data-ttu-id="2fd74-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-581">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-581">Int64</span></span>|  
|<span data-ttu-id="2fd74-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="2fd74-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-583">Boolean</span></span>|  
|<span data-ttu-id="2fd74-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2fd74-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="2fd74-585">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-585">String</span></span>|  
|<span data-ttu-id="2fd74-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2fd74-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="2fd74-587">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-587">Int64</span></span>|  
|<span data-ttu-id="2fd74-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-588">IS_NULLABLE</span></span>|<span data-ttu-id="2fd74-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-589">Boolean</span></span>|  
|<span data-ttu-id="2fd74-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-590">DATA_TYPE</span></span>|<span data-ttu-id="2fd74-591">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-591">Int32</span></span>|  
|<span data-ttu-id="2fd74-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-592">TYPE_GUID</span></span>|<span data-ttu-id="2fd74-593">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-593">Guid</span></span>|  
|<span data-ttu-id="2fd74-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="2fd74-595">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-595">Int64</span></span>|  
|<span data-ttu-id="2fd74-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2fd74-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="2fd74-597">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-597">Int64</span></span>|  
|<span data-ttu-id="2fd74-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="2fd74-599">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-599">Int32</span></span>|  
|<span data-ttu-id="2fd74-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="2fd74-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="2fd74-601">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-601">Int16</span></span>|  
|<span data-ttu-id="2fd74-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="2fd74-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="2fd74-603">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-603">Int64</span></span>|  
|<span data-ttu-id="2fd74-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="2fd74-605">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-605">String</span></span>|  
|<span data-ttu-id="2fd74-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="2fd74-607">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-607">String</span></span>|  
|<span data-ttu-id="2fd74-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="2fd74-609">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-609">String</span></span>|  
|<span data-ttu-id="2fd74-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="2fd74-611">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-611">String</span></span>|  
|<span data-ttu-id="2fd74-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="2fd74-613">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-613">String</span></span>|  
|<span data-ttu-id="2fd74-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-614">COLLATION_NAME</span></span>|<span data-ttu-id="2fd74-615">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-615">String</span></span>|  
|<span data-ttu-id="2fd74-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="2fd74-617">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-617">String</span></span>|  
|<span data-ttu-id="2fd74-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="2fd74-619">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-619">String</span></span>|  
|<span data-ttu-id="2fd74-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-620">DOMAIN_NAME</span></span>|<span data-ttu-id="2fd74-621">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-621">String</span></span>|  
|<span data-ttu-id="2fd74-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-622">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-623">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="2fd74-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2fd74-624">Procedures</span></span>  
  
|<span data-ttu-id="2fd74-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-625">ColumnName</span></span>|<span data-ttu-id="2fd74-626">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="2fd74-628">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-628">String</span></span>|  
|<span data-ttu-id="2fd74-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="2fd74-630">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-630">String</span></span>|  
|<span data-ttu-id="2fd74-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="2fd74-632">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-632">String</span></span>|  
|<span data-ttu-id="2fd74-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2fd74-634">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-634">Int16</span></span>|  
|<span data-ttu-id="2fd74-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="2fd74-636">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-636">String</span></span>|  
|<span data-ttu-id="2fd74-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-637">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-638">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-638">String</span></span>|  
|<span data-ttu-id="2fd74-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-639">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-640">DateTime</span></span>|  
|<span data-ttu-id="2fd74-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-641">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="2fd74-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="2fd74-643">Views</span></span>  
  
|<span data-ttu-id="2fd74-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-644">ColumnName</span></span>|<span data-ttu-id="2fd74-645">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-646">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-647">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-647">String</span></span>|  
|<span data-ttu-id="2fd74-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-649">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-649">String</span></span>|  
|<span data-ttu-id="2fd74-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-650">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-651">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-651">String</span></span>|  
|<span data-ttu-id="2fd74-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="2fd74-653">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-653">String</span></span>|  
|<span data-ttu-id="2fd74-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-654">CHECK_OPTION</span></span>|<span data-ttu-id="2fd74-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-655">Boolean</span></span>|  
|<span data-ttu-id="2fd74-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="2fd74-656">IS_UPDATABLE</span></span>|<span data-ttu-id="2fd74-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-657">Boolean</span></span>|  
|<span data-ttu-id="2fd74-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2fd74-658">DESCRIPTION</span></span>|<span data-ttu-id="2fd74-659">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-659">String</span></span>|  
|<span data-ttu-id="2fd74-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-660">DATE_CREATED</span></span>|<span data-ttu-id="2fd74-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-661">DateTime</span></span>|  
|<span data-ttu-id="2fd74-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="2fd74-662">DATE_MODIFIED</span></span>|<span data-ttu-id="2fd74-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="2fd74-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="2fd74-664">Índices</span><span class="sxs-lookup"><span data-stu-id="2fd74-664">Indexes</span></span>  
  
|<span data-ttu-id="2fd74-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="2fd74-665">ColumnName</span></span>|<span data-ttu-id="2fd74-666">DataType</span><span class="sxs-lookup"><span data-stu-id="2fd74-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fd74-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-667">TABLE_CATALOG</span></span>|<span data-ttu-id="2fd74-668">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-668">String</span></span>|  
|<span data-ttu-id="2fd74-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="2fd74-670">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-670">String</span></span>|  
|<span data-ttu-id="2fd74-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-671">TABLE_NAME</span></span>|<span data-ttu-id="2fd74-672">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-672">String</span></span>|  
|<span data-ttu-id="2fd74-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2fd74-673">INDEX_CATALOG</span></span>|<span data-ttu-id="2fd74-674">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-674">String</span></span>|  
|<span data-ttu-id="2fd74-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2fd74-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="2fd74-676">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-676">String</span></span>|  
|<span data-ttu-id="2fd74-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-677">INDEX_NAME</span></span>|<span data-ttu-id="2fd74-678">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-678">String</span></span>|  
|<span data-ttu-id="2fd74-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="2fd74-679">PRIMARY_KEY</span></span>|<span data-ttu-id="2fd74-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-680">Boolean</span></span>|  
|<span data-ttu-id="2fd74-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2fd74-681">UNIQUE</span></span>|<span data-ttu-id="2fd74-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-682">Boolean</span></span>|  
|<span data-ttu-id="2fd74-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="2fd74-683">CLUSTERED</span></span>|<span data-ttu-id="2fd74-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-684">Boolean</span></span>|  
|<span data-ttu-id="2fd74-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="2fd74-685">TYPE</span></span>|<span data-ttu-id="2fd74-686">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-686">Int32</span></span>|  
|<span data-ttu-id="2fd74-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="2fd74-687">FILL_FACTOR</span></span>|<span data-ttu-id="2fd74-688">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-688">Int32</span></span>|  
|<span data-ttu-id="2fd74-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="2fd74-689">INITIAL_SIZE</span></span>|<span data-ttu-id="2fd74-690">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-690">Int32</span></span>|  
|<span data-ttu-id="2fd74-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="2fd74-691">NULLS</span></span>|<span data-ttu-id="2fd74-692">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-692">Int32</span></span>|  
|<span data-ttu-id="2fd74-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="2fd74-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="2fd74-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-694">Boolean</span></span>|  
|<span data-ttu-id="2fd74-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2fd74-695">AUTO_UPDATE</span></span>|<span data-ttu-id="2fd74-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-696">Boolean</span></span>|  
|<span data-ttu-id="2fd74-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-697">NULL_COLLATION</span></span>|<span data-ttu-id="2fd74-698">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-698">Int32</span></span>|  
|<span data-ttu-id="2fd74-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="2fd74-700">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-700">Int64</span></span>|  
|<span data-ttu-id="2fd74-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2fd74-701">COLUMN_NAME</span></span>|<span data-ttu-id="2fd74-702">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-702">String</span></span>|  
|<span data-ttu-id="2fd74-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-703">COLUMN_GUID</span></span>|<span data-ttu-id="2fd74-704">GUID</span><span class="sxs-lookup"><span data-stu-id="2fd74-704">Guid</span></span>|  
|<span data-ttu-id="2fd74-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="2fd74-705">COLUMN_PROPID</span></span>|<span data-ttu-id="2fd74-706">Int64</span><span class="sxs-lookup"><span data-stu-id="2fd74-706">Int64</span></span>|  
|<span data-ttu-id="2fd74-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2fd74-707">COLLATION</span></span>|<span data-ttu-id="2fd74-708">Int16</span><span class="sxs-lookup"><span data-stu-id="2fd74-708">Int16</span></span>|  
|<span data-ttu-id="2fd74-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2fd74-709">CARDINALITY</span></span>|<span data-ttu-id="2fd74-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="2fd74-710">Decimal</span></span>|  
|<span data-ttu-id="2fd74-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="2fd74-711">PAGES</span></span>|<span data-ttu-id="2fd74-712">Int32</span><span class="sxs-lookup"><span data-stu-id="2fd74-712">Int32</span></span>|  
|<span data-ttu-id="2fd74-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2fd74-713">FILTER_CONDITION</span></span>|<span data-ttu-id="2fd74-714">String</span><span class="sxs-lookup"><span data-stu-id="2fd74-714">String</span></span>|  
|<span data-ttu-id="2fd74-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="2fd74-715">INTEGRATED</span></span>|<span data-ttu-id="2fd74-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="2fd74-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fd74-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fd74-717">See also</span></span>

- [<span data-ttu-id="2fd74-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="2fd74-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

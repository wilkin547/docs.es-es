---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783447"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="cb9ff-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="cb9ff-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="cb9ff-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="cb9ff-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="cb9ff-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb9ff-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="cb9ff-105">El controlador de OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="cb9ff-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="cb9ff-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-106">Tables</span></span>  
  
- <span data-ttu-id="cb9ff-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-107">Columns</span></span>  
  
- <span data-ttu-id="cb9ff-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cb9ff-108">Procedures</span></span>  
  
- <span data-ttu-id="cb9ff-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cb9ff-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="cb9ff-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="cb9ff-110">Catalog</span></span>  
  
- <span data-ttu-id="cb9ff-111">Índices</span><span class="sxs-lookup"><span data-stu-id="cb9ff-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="cb9ff-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-112">Tables</span></span>  
  
|<span data-ttu-id="cb9ff-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-113">ColumnName</span></span>|<span data-ttu-id="cb9ff-114">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-115">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-116">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-116">String</span></span>|  
|<span data-ttu-id="cb9ff-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-118">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-118">String</span></span>|  
|<span data-ttu-id="cb9ff-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-119">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-120">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-120">String</span></span>|  
|<span data-ttu-id="cb9ff-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-121">TABLE_TYPE</span></span>|<span data-ttu-id="cb9ff-122">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-122">String</span></span>|  
|<span data-ttu-id="cb9ff-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-123">TABLE_GUID</span></span>|<span data-ttu-id="cb9ff-124">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-124">Guid</span></span>|  
|<span data-ttu-id="cb9ff-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-125">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-126">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-126">String</span></span>|  
|<span data-ttu-id="cb9ff-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-127">TABLE_PROPID</span></span>|<span data-ttu-id="cb9ff-128">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-128">Int64</span></span>|  
|<span data-ttu-id="cb9ff-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-129">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-130">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-131">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cb9ff-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-133">Columns</span></span>  
  
|<span data-ttu-id="cb9ff-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-134">ColumnName</span></span>|<span data-ttu-id="cb9ff-135">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-136">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-137">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-137">String</span></span>|  
|<span data-ttu-id="cb9ff-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-139">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-139">String</span></span>|  
|<span data-ttu-id="cb9ff-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-140">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-141">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-141">String</span></span>|  
|<span data-ttu-id="cb9ff-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-142">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-143">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-143">String</span></span>|  
|<span data-ttu-id="cb9ff-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-144">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-145">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-145">Guid</span></span>|  
|<span data-ttu-id="cb9ff-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-146">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-147">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-147">Int64</span></span>|  
|<span data-ttu-id="cb9ff-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-149">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-149">Int64</span></span>|  
|<span data-ttu-id="cb9ff-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="cb9ff-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-151">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="cb9ff-153">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-153">String</span></span>|  
|<span data-ttu-id="cb9ff-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="cb9ff-155">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-155">Int64</span></span>|  
|<span data-ttu-id="cb9ff-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-156">IS_NULLABLE</span></span>|<span data-ttu-id="cb9ff-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-157">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-158">DATA_TYPE</span></span>|<span data-ttu-id="cb9ff-159">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-159">Int32</span></span>|  
|<span data-ttu-id="cb9ff-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-160">TYPE_GUID</span></span>|<span data-ttu-id="cb9ff-161">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-161">Guid</span></span>|  
|<span data-ttu-id="cb9ff-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="cb9ff-163">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-163">Int64</span></span>|  
|<span data-ttu-id="cb9ff-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="cb9ff-165">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-165">Int64</span></span>|  
|<span data-ttu-id="cb9ff-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="cb9ff-167">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-167">Int32</span></span>|  
|<span data-ttu-id="cb9ff-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="cb9ff-169">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-169">Int16</span></span>|  
|<span data-ttu-id="cb9ff-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="cb9ff-171">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-171">Int64</span></span>|  
|<span data-ttu-id="cb9ff-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="cb9ff-173">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-173">String</span></span>|  
|<span data-ttu-id="cb9ff-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="cb9ff-175">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-175">String</span></span>|  
|<span data-ttu-id="cb9ff-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="cb9ff-177">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-177">String</span></span>|  
|<span data-ttu-id="cb9ff-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="cb9ff-179">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-179">String</span></span>|  
|<span data-ttu-id="cb9ff-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="cb9ff-181">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-181">String</span></span>|  
|<span data-ttu-id="cb9ff-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-182">COLLATION_NAME</span></span>|<span data-ttu-id="cb9ff-183">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-183">String</span></span>|  
|<span data-ttu-id="cb9ff-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="cb9ff-185">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-185">String</span></span>|  
|<span data-ttu-id="cb9ff-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="cb9ff-187">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-187">String</span></span>|  
|<span data-ttu-id="cb9ff-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-188">DOMAIN_NAME</span></span>|<span data-ttu-id="cb9ff-189">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-189">String</span></span>|  
|<span data-ttu-id="cb9ff-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-190">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-191">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-191">String</span></span>|  
|<span data-ttu-id="cb9ff-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-192">COLUMN_LCID</span></span>|<span data-ttu-id="cb9ff-193">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-193">Int32</span></span>|  
|<span data-ttu-id="cb9ff-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="cb9ff-195">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-195">Int32</span></span>|  
|<span data-ttu-id="cb9ff-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-196">COLUMN_SORTID</span></span>|<span data-ttu-id="cb9ff-197">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-197">Int32</span></span>|  
|<span data-ttu-id="cb9ff-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="cb9ff-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="cb9ff-199">Byte[]</span></span>|  
|<span data-ttu-id="cb9ff-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-200">IS_COMPUTED</span></span>|<span data-ttu-id="cb9ff-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cb9ff-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cb9ff-202">Procedures</span></span>  
  
|<span data-ttu-id="cb9ff-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-203">ColumnName</span></span>|<span data-ttu-id="cb9ff-204">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="cb9ff-206">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-206">String</span></span>|  
|<span data-ttu-id="cb9ff-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-208">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-208">String</span></span>|  
|<span data-ttu-id="cb9ff-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="cb9ff-210">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-210">String</span></span>|  
|<span data-ttu-id="cb9ff-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="cb9ff-212">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-212">Int16</span></span>|  
|<span data-ttu-id="cb9ff-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="cb9ff-214">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-214">String</span></span>|  
|<span data-ttu-id="cb9ff-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-215">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-216">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-216">String</span></span>|  
|<span data-ttu-id="cb9ff-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-217">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-218">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-219">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="cb9ff-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cb9ff-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="cb9ff-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-222">ColumnName</span></span>|<span data-ttu-id="cb9ff-223">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="cb9ff-225">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-225">String</span></span>|  
|<span data-ttu-id="cb9ff-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-227">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-227">String</span></span>|  
|<span data-ttu-id="cb9ff-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="cb9ff-229">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-229">String</span></span>|  
|<span data-ttu-id="cb9ff-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-230">PARAMETER_NAME</span></span>|<span data-ttu-id="cb9ff-231">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-231">String</span></span>|  
|<span data-ttu-id="cb9ff-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-233">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-233">Int32</span></span>|  
|<span data-ttu-id="cb9ff-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="cb9ff-235">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-235">Int32</span></span>|  
|<span data-ttu-id="cb9ff-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="cb9ff-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-237">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="cb9ff-239">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-239">String</span></span>|  
|<span data-ttu-id="cb9ff-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-240">IS_NULLABLE</span></span>|<span data-ttu-id="cb9ff-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-241">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-242">DATA_TYPE</span></span>|<span data-ttu-id="cb9ff-243">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-243">Int32</span></span>|  
|<span data-ttu-id="cb9ff-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="cb9ff-245">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-245">Int64</span></span>|  
|<span data-ttu-id="cb9ff-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="cb9ff-247">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-247">Int64</span></span>|  
|<span data-ttu-id="cb9ff-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="cb9ff-249">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-249">Int32</span></span>|  
|<span data-ttu-id="cb9ff-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="cb9ff-251">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-251">Int16</span></span>|  
|<span data-ttu-id="cb9ff-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-252">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-253">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-253">String</span></span>|  
|<span data-ttu-id="cb9ff-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-254">TYPE_NAME</span></span>|<span data-ttu-id="cb9ff-255">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-255">String</span></span>|  
|<span data-ttu-id="cb9ff-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="cb9ff-257">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="cb9ff-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="cb9ff-258">Catalog</span></span>  
  
|<span data-ttu-id="cb9ff-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-259">ColumnName</span></span>|<span data-ttu-id="cb9ff-260">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-261">CATALOG_NAME</span></span>|<span data-ttu-id="cb9ff-262">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-262">String</span></span>|  
|<span data-ttu-id="cb9ff-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-263">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-264">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="cb9ff-265">Índices</span><span class="sxs-lookup"><span data-stu-id="cb9ff-265">Indexes</span></span>  
  
|<span data-ttu-id="cb9ff-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-266">ColumnName</span></span>|<span data-ttu-id="cb9ff-267">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-268">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-269">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-269">String</span></span>|  
|<span data-ttu-id="cb9ff-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-271">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-271">String</span></span>|  
|<span data-ttu-id="cb9ff-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-272">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-273">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-273">String</span></span>|  
|<span data-ttu-id="cb9ff-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-274">INDEX_CATALOG</span></span>|<span data-ttu-id="cb9ff-275">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-275">String</span></span>|  
|<span data-ttu-id="cb9ff-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="cb9ff-277">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-277">String</span></span>|  
|<span data-ttu-id="cb9ff-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-278">INDEX_NAME</span></span>|<span data-ttu-id="cb9ff-279">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-279">String</span></span>|  
|<span data-ttu-id="cb9ff-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="cb9ff-280">PRIMARY_KEY</span></span>|<span data-ttu-id="cb9ff-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-281">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-282">UNIQUE</span></span>|<span data-ttu-id="cb9ff-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-283">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-284">CLUSTERED</span></span>|<span data-ttu-id="cb9ff-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-285">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-286">TYPE</span></span>|<span data-ttu-id="cb9ff-287">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-287">Int32</span></span>|  
|<span data-ttu-id="cb9ff-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="cb9ff-288">FILL_FACTOR</span></span>|<span data-ttu-id="cb9ff-289">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-289">Int32</span></span>|  
|<span data-ttu-id="cb9ff-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-290">INITIAL_SIZE</span></span>|<span data-ttu-id="cb9ff-291">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-291">Int32</span></span>|  
|<span data-ttu-id="cb9ff-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-292">NULLS</span></span>|<span data-ttu-id="cb9ff-293">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-293">Int32</span></span>|  
|<span data-ttu-id="cb9ff-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="cb9ff-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-295">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-296">AUTO_UPDATE</span></span>|<span data-ttu-id="cb9ff-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-297">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-298">NULL_COLLATION</span></span>|<span data-ttu-id="cb9ff-299">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-299">Int32</span></span>|  
|<span data-ttu-id="cb9ff-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-301">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-301">Int64</span></span>|  
|<span data-ttu-id="cb9ff-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-302">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-303">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-303">String</span></span>|  
|<span data-ttu-id="cb9ff-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-304">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-305">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-305">Guid</span></span>|  
|<span data-ttu-id="cb9ff-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-306">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-307">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-307">Int64</span></span>|  
|<span data-ttu-id="cb9ff-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-308">COLLATION</span></span>|<span data-ttu-id="cb9ff-309">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-309">Int16</span></span>|  
|<span data-ttu-id="cb9ff-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="cb9ff-310">CARDINALITY</span></span>|<span data-ttu-id="cb9ff-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="cb9ff-311">Decimal</span></span>|  
|<span data-ttu-id="cb9ff-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="cb9ff-312">PAGES</span></span>|<span data-ttu-id="cb9ff-313">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-313">Int32</span></span>|  
|<span data-ttu-id="cb9ff-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-314">FILTER_CONDITION</span></span>|<span data-ttu-id="cb9ff-315">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-315">String</span></span>|  
|<span data-ttu-id="cb9ff-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-316">INTEGRATED</span></span>|<span data-ttu-id="cb9ff-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="cb9ff-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="cb9ff-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="cb9ff-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="cb9ff-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="cb9ff-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-320">Tables</span></span>  
  
- <span data-ttu-id="cb9ff-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-321">Columns</span></span>  
  
- <span data-ttu-id="cb9ff-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cb9ff-322">Procedures</span></span>  
  
- <span data-ttu-id="cb9ff-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cb9ff-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="cb9ff-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cb9ff-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="cb9ff-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-325">Views</span></span>  
  
- <span data-ttu-id="cb9ff-326">Índices</span><span class="sxs-lookup"><span data-stu-id="cb9ff-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="cb9ff-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-327">Tables</span></span>  
  
|<span data-ttu-id="cb9ff-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-328">ColumnName</span></span>|<span data-ttu-id="cb9ff-329">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-330">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-331">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-331">String</span></span>|  
|<span data-ttu-id="cb9ff-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-333">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-333">String</span></span>|  
|<span data-ttu-id="cb9ff-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-334">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-335">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-335">String</span></span>|  
|<span data-ttu-id="cb9ff-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-336">TABLE_TYPE</span></span>|<span data-ttu-id="cb9ff-337">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-337">String</span></span>|  
|<span data-ttu-id="cb9ff-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-338">TABLE_GUID</span></span>|<span data-ttu-id="cb9ff-339">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-339">Guid</span></span>|  
|<span data-ttu-id="cb9ff-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-340">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-341">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-341">String</span></span>|  
|<span data-ttu-id="cb9ff-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-342">TABLE_PROPID</span></span>|<span data-ttu-id="cb9ff-343">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-343">Int64</span></span>|  
|<span data-ttu-id="cb9ff-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-344">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-345">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-346">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cb9ff-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-348">Columns</span></span>  
  
|<span data-ttu-id="cb9ff-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-349">ColumnName</span></span>|<span data-ttu-id="cb9ff-350">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-351">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-352">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-352">String</span></span>|  
|<span data-ttu-id="cb9ff-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-354">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-354">String</span></span>|  
|<span data-ttu-id="cb9ff-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-355">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-356">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-356">String</span></span>|  
|<span data-ttu-id="cb9ff-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-357">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-358">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-358">String</span></span>|  
|<span data-ttu-id="cb9ff-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-359">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-360">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-360">Guid</span></span>|  
|<span data-ttu-id="cb9ff-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-361">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-362">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-362">Int64</span></span>|  
|<span data-ttu-id="cb9ff-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-364">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-364">Int64</span></span>|  
|<span data-ttu-id="cb9ff-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="cb9ff-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-366">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="cb9ff-368">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-368">String</span></span>|  
|<span data-ttu-id="cb9ff-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="cb9ff-370">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-370">Int64</span></span>|  
|<span data-ttu-id="cb9ff-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-371">IS_NULLABLE</span></span>|<span data-ttu-id="cb9ff-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-372">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-373">DATA_TYPE</span></span>|<span data-ttu-id="cb9ff-374">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-374">Int32</span></span>|  
|<span data-ttu-id="cb9ff-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-375">TYPE_GUID</span></span>|<span data-ttu-id="cb9ff-376">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-376">Guid</span></span>|  
|<span data-ttu-id="cb9ff-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="cb9ff-378">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-378">Int64</span></span>|  
|<span data-ttu-id="cb9ff-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="cb9ff-380">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-380">Int64</span></span>|  
|<span data-ttu-id="cb9ff-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="cb9ff-382">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-382">Int32</span></span>|  
|<span data-ttu-id="cb9ff-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="cb9ff-384">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-384">Int16</span></span>|  
|<span data-ttu-id="cb9ff-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="cb9ff-386">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-386">Int64</span></span>|  
|<span data-ttu-id="cb9ff-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="cb9ff-388">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-388">String</span></span>|  
|<span data-ttu-id="cb9ff-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="cb9ff-390">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-390">String</span></span>|  
|<span data-ttu-id="cb9ff-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="cb9ff-392">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-392">String</span></span>|  
|<span data-ttu-id="cb9ff-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="cb9ff-394">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-394">String</span></span>|  
|<span data-ttu-id="cb9ff-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="cb9ff-396">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-396">String</span></span>|  
|<span data-ttu-id="cb9ff-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-397">COLLATION_NAME</span></span>|<span data-ttu-id="cb9ff-398">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-398">String</span></span>|  
|<span data-ttu-id="cb9ff-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="cb9ff-400">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-400">String</span></span>|  
|<span data-ttu-id="cb9ff-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="cb9ff-402">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-402">String</span></span>|  
|<span data-ttu-id="cb9ff-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-403">DOMAIN_NAME</span></span>|<span data-ttu-id="cb9ff-404">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-404">String</span></span>|  
|<span data-ttu-id="cb9ff-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-405">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-406">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cb9ff-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cb9ff-407">Procedures</span></span>  
  
|<span data-ttu-id="cb9ff-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-408">ColumnName</span></span>|<span data-ttu-id="cb9ff-409">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="cb9ff-411">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-411">String</span></span>|  
|<span data-ttu-id="cb9ff-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-413">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-413">String</span></span>|  
|<span data-ttu-id="cb9ff-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="cb9ff-415">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-415">String</span></span>|  
|<span data-ttu-id="cb9ff-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="cb9ff-417">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-417">Int16</span></span>|  
|<span data-ttu-id="cb9ff-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="cb9ff-419">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-419">String</span></span>|  
|<span data-ttu-id="cb9ff-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-420">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-421">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-421">String</span></span>|  
|<span data-ttu-id="cb9ff-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-422">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-423">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-424">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="cb9ff-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cb9ff-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="cb9ff-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-427">ColumnName</span></span>|<span data-ttu-id="cb9ff-428">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="cb9ff-430">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-430">String</span></span>|  
|<span data-ttu-id="cb9ff-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-432">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-432">String</span></span>|  
|<span data-ttu-id="cb9ff-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="cb9ff-434">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-434">String</span></span>|  
|<span data-ttu-id="cb9ff-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-435">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-436">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-436">String</span></span>|  
|<span data-ttu-id="cb9ff-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-437">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-438">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-438">Guid</span></span>|  
|<span data-ttu-id="cb9ff-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-439">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-440">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-440">Int64</span></span>|  
|<span data-ttu-id="cb9ff-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="cb9ff-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="cb9ff-442">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-442">Int64</span></span>|  
|<span data-ttu-id="cb9ff-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-444">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-444">Int64</span></span>|  
|<span data-ttu-id="cb9ff-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-445">IS_NULLABLE</span></span>|<span data-ttu-id="cb9ff-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-446">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-447">DATA_TYPE</span></span>|<span data-ttu-id="cb9ff-448">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-448">Int32</span></span>|  
|<span data-ttu-id="cb9ff-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-449">TYPE_GUID</span></span>|<span data-ttu-id="cb9ff-450">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-450">Guid</span></span>|  
|<span data-ttu-id="cb9ff-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="cb9ff-452">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-452">Int64</span></span>|  
|<span data-ttu-id="cb9ff-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="cb9ff-454">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-454">Int64</span></span>|  
|<span data-ttu-id="cb9ff-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="cb9ff-456">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-456">Int32</span></span>|  
|<span data-ttu-id="cb9ff-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="cb9ff-458">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-458">Int16</span></span>|  
|<span data-ttu-id="cb9ff-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-459">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-460">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-460">String</span></span>|  
|<span data-ttu-id="cb9ff-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="cb9ff-461">OVERLOAD</span></span>|<span data-ttu-id="cb9ff-462">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="cb9ff-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-463">Views</span></span>  
  
|<span data-ttu-id="cb9ff-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-464">ColumnName</span></span>|<span data-ttu-id="cb9ff-465">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-466">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-467">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-467">String</span></span>|  
|<span data-ttu-id="cb9ff-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-469">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-469">String</span></span>|  
|<span data-ttu-id="cb9ff-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-470">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-471">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-471">String</span></span>|  
|<span data-ttu-id="cb9ff-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="cb9ff-473">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-473">String</span></span>|  
|<span data-ttu-id="cb9ff-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-474">CHECK_OPTION</span></span>|<span data-ttu-id="cb9ff-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-475">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-476">IS_UPDATABLE</span></span>|<span data-ttu-id="cb9ff-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-477">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-478">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-479">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-479">String</span></span>|  
|<span data-ttu-id="cb9ff-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-480">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-481">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-482">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="cb9ff-484">Índices</span><span class="sxs-lookup"><span data-stu-id="cb9ff-484">Indexes</span></span>  
  
|<span data-ttu-id="cb9ff-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-485">ColumnName</span></span>|<span data-ttu-id="cb9ff-486">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-487">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-488">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-488">String</span></span>|  
|<span data-ttu-id="cb9ff-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-490">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-490">String</span></span>|  
|<span data-ttu-id="cb9ff-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-491">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-492">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-492">String</span></span>|  
|<span data-ttu-id="cb9ff-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-493">INDEX_CATALOG</span></span>|<span data-ttu-id="cb9ff-494">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-494">String</span></span>|  
|<span data-ttu-id="cb9ff-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="cb9ff-496">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-496">String</span></span>|  
|<span data-ttu-id="cb9ff-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-497">INDEX_NAME</span></span>|<span data-ttu-id="cb9ff-498">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-498">String</span></span>|  
|<span data-ttu-id="cb9ff-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="cb9ff-499">PRIMARY_KEY</span></span>|<span data-ttu-id="cb9ff-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-500">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-501">UNIQUE</span></span>|<span data-ttu-id="cb9ff-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-502">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-503">CLUSTERED</span></span>|<span data-ttu-id="cb9ff-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-504">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-505">TYPE</span></span>|<span data-ttu-id="cb9ff-506">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-506">Int32</span></span>|  
|<span data-ttu-id="cb9ff-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="cb9ff-507">FILL_FACTOR</span></span>|<span data-ttu-id="cb9ff-508">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-508">Int32</span></span>|  
|<span data-ttu-id="cb9ff-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-509">INITIAL_SIZE</span></span>|<span data-ttu-id="cb9ff-510">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-510">Int32</span></span>|  
|<span data-ttu-id="cb9ff-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-511">NULLS</span></span>|<span data-ttu-id="cb9ff-512">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-512">Int32</span></span>|  
|<span data-ttu-id="cb9ff-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="cb9ff-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-514">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-515">AUTO_UPDATE</span></span>|<span data-ttu-id="cb9ff-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-516">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-517">NULL_COLLATION</span></span>|<span data-ttu-id="cb9ff-518">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-518">Int32</span></span>|  
|<span data-ttu-id="cb9ff-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-520">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-520">Int64</span></span>|  
|<span data-ttu-id="cb9ff-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-521">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-522">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-522">String</span></span>|  
|<span data-ttu-id="cb9ff-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-523">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-524">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-524">Guid</span></span>|  
|<span data-ttu-id="cb9ff-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-525">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-526">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-526">Int64</span></span>|  
|<span data-ttu-id="cb9ff-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-527">COLLATION</span></span>|<span data-ttu-id="cb9ff-528">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-528">Int16</span></span>|  
|<span data-ttu-id="cb9ff-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="cb9ff-529">CARDINALITY</span></span>|<span data-ttu-id="cb9ff-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="cb9ff-530">Decimal</span></span>|  
|<span data-ttu-id="cb9ff-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="cb9ff-531">PAGES</span></span>|<span data-ttu-id="cb9ff-532">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-532">Int32</span></span>|  
|<span data-ttu-id="cb9ff-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-533">FILTER_CONDITION</span></span>|<span data-ttu-id="cb9ff-534">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-534">String</span></span>|  
|<span data-ttu-id="cb9ff-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-535">INTEGRATED</span></span>|<span data-ttu-id="cb9ff-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="cb9ff-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="cb9ff-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="cb9ff-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="cb9ff-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="cb9ff-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-539">Tables</span></span>  
  
- <span data-ttu-id="cb9ff-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-540">Columns</span></span>  
  
- <span data-ttu-id="cb9ff-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cb9ff-541">Procedures</span></span>  
  
- <span data-ttu-id="cb9ff-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-542">Views</span></span>  
  
- <span data-ttu-id="cb9ff-543">Índices</span><span class="sxs-lookup"><span data-stu-id="cb9ff-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="cb9ff-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-544">Tables</span></span>  
  
|<span data-ttu-id="cb9ff-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-545">ColumnName</span></span>|<span data-ttu-id="cb9ff-546">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-547">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-548">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-548">String</span></span>|  
|<span data-ttu-id="cb9ff-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-550">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-550">String</span></span>|  
|<span data-ttu-id="cb9ff-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-551">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-552">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-552">String</span></span>|  
|<span data-ttu-id="cb9ff-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-553">TABLE_TYPE</span></span>|<span data-ttu-id="cb9ff-554">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-554">String</span></span>|  
|<span data-ttu-id="cb9ff-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-555">TABLE_GUID</span></span>|<span data-ttu-id="cb9ff-556">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-556">Guid</span></span>|  
|<span data-ttu-id="cb9ff-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-557">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-558">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-558">String</span></span>|  
|<span data-ttu-id="cb9ff-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-559">TABLE_PROPID</span></span>|<span data-ttu-id="cb9ff-560">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-560">Int64</span></span>|  
|<span data-ttu-id="cb9ff-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-561">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-562">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-563">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cb9ff-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-565">Columns</span></span>  
  
|<span data-ttu-id="cb9ff-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-566">ColumnName</span></span>|<span data-ttu-id="cb9ff-567">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-568">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-569">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-569">String</span></span>|  
|<span data-ttu-id="cb9ff-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-571">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-571">String</span></span>|  
|<span data-ttu-id="cb9ff-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-572">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-573">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-573">String</span></span>|  
|<span data-ttu-id="cb9ff-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-574">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-575">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-575">String</span></span>|  
|<span data-ttu-id="cb9ff-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-576">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-577">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-577">Guid</span></span>|  
|<span data-ttu-id="cb9ff-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-578">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-579">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-579">Int64</span></span>|  
|<span data-ttu-id="cb9ff-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-581">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-581">Int64</span></span>|  
|<span data-ttu-id="cb9ff-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="cb9ff-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-583">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="cb9ff-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="cb9ff-585">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-585">String</span></span>|  
|<span data-ttu-id="cb9ff-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="cb9ff-587">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-587">Int64</span></span>|  
|<span data-ttu-id="cb9ff-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-588">IS_NULLABLE</span></span>|<span data-ttu-id="cb9ff-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-589">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-590">DATA_TYPE</span></span>|<span data-ttu-id="cb9ff-591">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-591">Int32</span></span>|  
|<span data-ttu-id="cb9ff-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-592">TYPE_GUID</span></span>|<span data-ttu-id="cb9ff-593">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-593">Guid</span></span>|  
|<span data-ttu-id="cb9ff-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="cb9ff-595">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-595">Int64</span></span>|  
|<span data-ttu-id="cb9ff-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cb9ff-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="cb9ff-597">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-597">Int64</span></span>|  
|<span data-ttu-id="cb9ff-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="cb9ff-599">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-599">Int32</span></span>|  
|<span data-ttu-id="cb9ff-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="cb9ff-601">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-601">Int16</span></span>|  
|<span data-ttu-id="cb9ff-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="cb9ff-603">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-603">Int64</span></span>|  
|<span data-ttu-id="cb9ff-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="cb9ff-605">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-605">String</span></span>|  
|<span data-ttu-id="cb9ff-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="cb9ff-607">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-607">String</span></span>|  
|<span data-ttu-id="cb9ff-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="cb9ff-609">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-609">String</span></span>|  
|<span data-ttu-id="cb9ff-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="cb9ff-611">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-611">String</span></span>|  
|<span data-ttu-id="cb9ff-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="cb9ff-613">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-613">String</span></span>|  
|<span data-ttu-id="cb9ff-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-614">COLLATION_NAME</span></span>|<span data-ttu-id="cb9ff-615">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-615">String</span></span>|  
|<span data-ttu-id="cb9ff-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="cb9ff-617">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-617">String</span></span>|  
|<span data-ttu-id="cb9ff-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="cb9ff-619">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-619">String</span></span>|  
|<span data-ttu-id="cb9ff-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-620">DOMAIN_NAME</span></span>|<span data-ttu-id="cb9ff-621">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-621">String</span></span>|  
|<span data-ttu-id="cb9ff-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-622">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-623">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cb9ff-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cb9ff-624">Procedures</span></span>  
  
|<span data-ttu-id="cb9ff-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-625">ColumnName</span></span>|<span data-ttu-id="cb9ff-626">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="cb9ff-628">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-628">String</span></span>|  
|<span data-ttu-id="cb9ff-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-630">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-630">String</span></span>|  
|<span data-ttu-id="cb9ff-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="cb9ff-632">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-632">String</span></span>|  
|<span data-ttu-id="cb9ff-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="cb9ff-634">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-634">Int16</span></span>|  
|<span data-ttu-id="cb9ff-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="cb9ff-636">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-636">String</span></span>|  
|<span data-ttu-id="cb9ff-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-637">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-638">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-638">String</span></span>|  
|<span data-ttu-id="cb9ff-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-639">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-640">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-641">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="cb9ff-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="cb9ff-643">Views</span></span>  
  
|<span data-ttu-id="cb9ff-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-644">ColumnName</span></span>|<span data-ttu-id="cb9ff-645">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-646">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-647">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-647">String</span></span>|  
|<span data-ttu-id="cb9ff-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-649">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-649">String</span></span>|  
|<span data-ttu-id="cb9ff-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-650">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-651">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-651">String</span></span>|  
|<span data-ttu-id="cb9ff-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="cb9ff-653">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-653">String</span></span>|  
|<span data-ttu-id="cb9ff-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-654">CHECK_OPTION</span></span>|<span data-ttu-id="cb9ff-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-655">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-656">IS_UPDATABLE</span></span>|<span data-ttu-id="cb9ff-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-657">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-658">DESCRIPTION</span></span>|<span data-ttu-id="cb9ff-659">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-659">String</span></span>|  
|<span data-ttu-id="cb9ff-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-660">DATE_CREATED</span></span>|<span data-ttu-id="cb9ff-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-661">DateTime</span></span>|  
|<span data-ttu-id="cb9ff-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-662">DATE_MODIFIED</span></span>|<span data-ttu-id="cb9ff-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="cb9ff-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="cb9ff-664">Índices</span><span class="sxs-lookup"><span data-stu-id="cb9ff-664">Indexes</span></span>  
  
|<span data-ttu-id="cb9ff-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="cb9ff-665">ColumnName</span></span>|<span data-ttu-id="cb9ff-666">DataType</span><span class="sxs-lookup"><span data-stu-id="cb9ff-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cb9ff-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-667">TABLE_CATALOG</span></span>|<span data-ttu-id="cb9ff-668">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-668">String</span></span>|  
|<span data-ttu-id="cb9ff-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="cb9ff-670">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-670">String</span></span>|  
|<span data-ttu-id="cb9ff-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-671">TABLE_NAME</span></span>|<span data-ttu-id="cb9ff-672">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-672">String</span></span>|  
|<span data-ttu-id="cb9ff-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cb9ff-673">INDEX_CATALOG</span></span>|<span data-ttu-id="cb9ff-674">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-674">String</span></span>|  
|<span data-ttu-id="cb9ff-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cb9ff-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="cb9ff-676">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-676">String</span></span>|  
|<span data-ttu-id="cb9ff-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-677">INDEX_NAME</span></span>|<span data-ttu-id="cb9ff-678">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-678">String</span></span>|  
|<span data-ttu-id="cb9ff-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="cb9ff-679">PRIMARY_KEY</span></span>|<span data-ttu-id="cb9ff-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-680">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-681">UNIQUE</span></span>|<span data-ttu-id="cb9ff-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-682">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-683">CLUSTERED</span></span>|<span data-ttu-id="cb9ff-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-684">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-685">TYPE</span></span>|<span data-ttu-id="cb9ff-686">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-686">Int32</span></span>|  
|<span data-ttu-id="cb9ff-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="cb9ff-687">FILL_FACTOR</span></span>|<span data-ttu-id="cb9ff-688">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-688">Int32</span></span>|  
|<span data-ttu-id="cb9ff-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-689">INITIAL_SIZE</span></span>|<span data-ttu-id="cb9ff-690">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-690">Int32</span></span>|  
|<span data-ttu-id="cb9ff-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-691">NULLS</span></span>|<span data-ttu-id="cb9ff-692">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-692">Int32</span></span>|  
|<span data-ttu-id="cb9ff-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="cb9ff-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="cb9ff-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-694">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="cb9ff-695">AUTO_UPDATE</span></span>|<span data-ttu-id="cb9ff-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-696">Boolean</span></span>|  
|<span data-ttu-id="cb9ff-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-697">NULL_COLLATION</span></span>|<span data-ttu-id="cb9ff-698">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-698">Int32</span></span>|  
|<span data-ttu-id="cb9ff-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="cb9ff-700">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-700">Int64</span></span>|  
|<span data-ttu-id="cb9ff-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cb9ff-701">COLUMN_NAME</span></span>|<span data-ttu-id="cb9ff-702">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-702">String</span></span>|  
|<span data-ttu-id="cb9ff-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-703">COLUMN_GUID</span></span>|<span data-ttu-id="cb9ff-704">Guid</span><span class="sxs-lookup"><span data-stu-id="cb9ff-704">Guid</span></span>|  
|<span data-ttu-id="cb9ff-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="cb9ff-705">COLUMN_PROPID</span></span>|<span data-ttu-id="cb9ff-706">Int64</span><span class="sxs-lookup"><span data-stu-id="cb9ff-706">Int64</span></span>|  
|<span data-ttu-id="cb9ff-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-707">COLLATION</span></span>|<span data-ttu-id="cb9ff-708">Int16</span><span class="sxs-lookup"><span data-stu-id="cb9ff-708">Int16</span></span>|  
|<span data-ttu-id="cb9ff-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="cb9ff-709">CARDINALITY</span></span>|<span data-ttu-id="cb9ff-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="cb9ff-710">Decimal</span></span>|  
|<span data-ttu-id="cb9ff-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="cb9ff-711">PAGES</span></span>|<span data-ttu-id="cb9ff-712">Int32</span><span class="sxs-lookup"><span data-stu-id="cb9ff-712">Int32</span></span>|  
|<span data-ttu-id="cb9ff-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="cb9ff-713">FILTER_CONDITION</span></span>|<span data-ttu-id="cb9ff-714">string</span><span class="sxs-lookup"><span data-stu-id="cb9ff-714">String</span></span>|  
|<span data-ttu-id="cb9ff-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="cb9ff-715">INTEGRATED</span></span>|<span data-ttu-id="cb9ff-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="cb9ff-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb9ff-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb9ff-717">See also</span></span>

- [<span data-ttu-id="cb9ff-718">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cb9ff-718">ADO.NET Overview</span></span>](ado-net-overview.md)

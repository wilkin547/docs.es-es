---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186944"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="d8825-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="d8825-102">OLE DB Schema Collections</span></span>

<span data-ttu-id="d8825-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="d8825-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="d8825-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8825-104">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="d8825-105">El controlador OLE DB de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="d8825-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="d8825-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8825-106">Tables</span></span>  
  
- <span data-ttu-id="d8825-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8825-107">Columns</span></span>  
  
- <span data-ttu-id="d8825-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8825-108">Procedures</span></span>  
  
- <span data-ttu-id="d8825-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8825-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="d8825-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="d8825-110">Catalog</span></span>  
  
- <span data-ttu-id="d8825-111">Índices</span><span class="sxs-lookup"><span data-stu-id="d8825-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d8825-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8825-112">Tables</span></span>  
  
|<span data-ttu-id="d8825-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-113">ColumnName</span></span>|<span data-ttu-id="d8825-114">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-115">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-116">String</span><span class="sxs-lookup"><span data-stu-id="d8825-116">String</span></span>|  
|<span data-ttu-id="d8825-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-118">String</span><span class="sxs-lookup"><span data-stu-id="d8825-118">String</span></span>|  
|<span data-ttu-id="d8825-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-119">TABLE_NAME</span></span>|<span data-ttu-id="d8825-120">String</span><span class="sxs-lookup"><span data-stu-id="d8825-120">String</span></span>|  
|<span data-ttu-id="d8825-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-121">TABLE_TYPE</span></span>|<span data-ttu-id="d8825-122">String</span><span class="sxs-lookup"><span data-stu-id="d8825-122">String</span></span>|  
|<span data-ttu-id="d8825-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-123">TABLE_GUID</span></span>|<span data-ttu-id="d8825-124">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-124">Guid</span></span>|  
|<span data-ttu-id="d8825-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-125">DESCRIPTION</span></span>|<span data-ttu-id="d8825-126">String</span><span class="sxs-lookup"><span data-stu-id="d8825-126">String</span></span>|  
|<span data-ttu-id="d8825-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-127">TABLE_PROPID</span></span>|<span data-ttu-id="d8825-128">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-128">Int64</span></span>|  
|<span data-ttu-id="d8825-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-129">DATE_CREATED</span></span>|<span data-ttu-id="d8825-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-130">DateTime</span></span>|  
|<span data-ttu-id="d8825-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-131">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d8825-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8825-133">Columns</span></span>  
  
|<span data-ttu-id="d8825-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-134">ColumnName</span></span>|<span data-ttu-id="d8825-135">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-136">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-137">String</span><span class="sxs-lookup"><span data-stu-id="d8825-137">String</span></span>|  
|<span data-ttu-id="d8825-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-139">String</span><span class="sxs-lookup"><span data-stu-id="d8825-139">String</span></span>|  
|<span data-ttu-id="d8825-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-140">TABLE_NAME</span></span>|<span data-ttu-id="d8825-141">String</span><span class="sxs-lookup"><span data-stu-id="d8825-141">String</span></span>|  
|<span data-ttu-id="d8825-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-142">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-143">String</span><span class="sxs-lookup"><span data-stu-id="d8825-143">String</span></span>|  
|<span data-ttu-id="d8825-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-144">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-145">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-145">Guid</span></span>|  
|<span data-ttu-id="d8825-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-146">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-147">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-147">Int64</span></span>|  
|<span data-ttu-id="d8825-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-149">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-149">Int64</span></span>|  
|<span data-ttu-id="d8825-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d8825-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-151">Boolean</span></span>|  
|<span data-ttu-id="d8825-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d8825-153">String</span><span class="sxs-lookup"><span data-stu-id="d8825-153">String</span></span>|  
|<span data-ttu-id="d8825-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d8825-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="d8825-155">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-155">Int64</span></span>|  
|<span data-ttu-id="d8825-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-156">IS_NULLABLE</span></span>|<span data-ttu-id="d8825-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-157">Boolean</span></span>|  
|<span data-ttu-id="d8825-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-158">DATA_TYPE</span></span>|<span data-ttu-id="d8825-159">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-159">Int32</span></span>|  
|<span data-ttu-id="d8825-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-160">TYPE_GUID</span></span>|<span data-ttu-id="d8825-161">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-161">Guid</span></span>|  
|<span data-ttu-id="d8825-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d8825-163">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-163">Int64</span></span>|  
|<span data-ttu-id="d8825-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d8825-165">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-165">Int64</span></span>|  
|<span data-ttu-id="d8825-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d8825-167">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-167">Int32</span></span>|  
|<span data-ttu-id="d8825-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d8825-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="d8825-169">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-169">Int16</span></span>|  
|<span data-ttu-id="d8825-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="d8825-171">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-171">Int64</span></span>|  
|<span data-ttu-id="d8825-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d8825-173">String</span><span class="sxs-lookup"><span data-stu-id="d8825-173">String</span></span>|  
|<span data-ttu-id="d8825-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d8825-175">String</span><span class="sxs-lookup"><span data-stu-id="d8825-175">String</span></span>|  
|<span data-ttu-id="d8825-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d8825-177">String</span><span class="sxs-lookup"><span data-stu-id="d8825-177">String</span></span>|  
|<span data-ttu-id="d8825-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="d8825-179">String</span><span class="sxs-lookup"><span data-stu-id="d8825-179">String</span></span>|  
|<span data-ttu-id="d8825-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d8825-181">String</span><span class="sxs-lookup"><span data-stu-id="d8825-181">String</span></span>|  
|<span data-ttu-id="d8825-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-182">COLLATION_NAME</span></span>|<span data-ttu-id="d8825-183">String</span><span class="sxs-lookup"><span data-stu-id="d8825-183">String</span></span>|  
|<span data-ttu-id="d8825-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d8825-185">String</span><span class="sxs-lookup"><span data-stu-id="d8825-185">String</span></span>|  
|<span data-ttu-id="d8825-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d8825-187">String</span><span class="sxs-lookup"><span data-stu-id="d8825-187">String</span></span>|  
|<span data-ttu-id="d8825-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-188">DOMAIN_NAME</span></span>|<span data-ttu-id="d8825-189">String</span><span class="sxs-lookup"><span data-stu-id="d8825-189">String</span></span>|  
|<span data-ttu-id="d8825-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-190">DESCRIPTION</span></span>|<span data-ttu-id="d8825-191">String</span><span class="sxs-lookup"><span data-stu-id="d8825-191">String</span></span>|  
|<span data-ttu-id="d8825-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="d8825-192">COLUMN_LCID</span></span>|<span data-ttu-id="d8825-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-193">Int32</span></span>|  
|<span data-ttu-id="d8825-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="d8825-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="d8825-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-195">Int32</span></span>|  
|<span data-ttu-id="d8825-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="d8825-196">COLUMN_SORTID</span></span>|<span data-ttu-id="d8825-197">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-197">Int32</span></span>|  
|<span data-ttu-id="d8825-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="d8825-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="d8825-199">Byte[]</span></span>|  
|<span data-ttu-id="d8825-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="d8825-200">IS_COMPUTED</span></span>|<span data-ttu-id="d8825-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d8825-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8825-202">Procedures</span></span>  
  
|<span data-ttu-id="d8825-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-203">ColumnName</span></span>|<span data-ttu-id="d8825-204">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d8825-206">String</span><span class="sxs-lookup"><span data-stu-id="d8825-206">String</span></span>|  
|<span data-ttu-id="d8825-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d8825-208">String</span><span class="sxs-lookup"><span data-stu-id="d8825-208">String</span></span>|  
|<span data-ttu-id="d8825-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8825-210">String</span><span class="sxs-lookup"><span data-stu-id="d8825-210">String</span></span>|  
|<span data-ttu-id="d8825-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d8825-212">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-212">Int16</span></span>|  
|<span data-ttu-id="d8825-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d8825-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d8825-214">String</span><span class="sxs-lookup"><span data-stu-id="d8825-214">String</span></span>|  
|<span data-ttu-id="d8825-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-215">DESCRIPTION</span></span>|<span data-ttu-id="d8825-216">String</span><span class="sxs-lookup"><span data-stu-id="d8825-216">String</span></span>|  
|<span data-ttu-id="d8825-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-217">DATE_CREATED</span></span>|<span data-ttu-id="d8825-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-218">DateTime</span></span>|  
|<span data-ttu-id="d8825-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-219">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d8825-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8825-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d8825-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-222">ColumnName</span></span>|<span data-ttu-id="d8825-223">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d8825-225">String</span><span class="sxs-lookup"><span data-stu-id="d8825-225">String</span></span>|  
|<span data-ttu-id="d8825-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d8825-227">String</span><span class="sxs-lookup"><span data-stu-id="d8825-227">String</span></span>|  
|<span data-ttu-id="d8825-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8825-229">String</span><span class="sxs-lookup"><span data-stu-id="d8825-229">String</span></span>|  
|<span data-ttu-id="d8825-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-230">PARAMETER_NAME</span></span>|<span data-ttu-id="d8825-231">String</span><span class="sxs-lookup"><span data-stu-id="d8825-231">String</span></span>|  
|<span data-ttu-id="d8825-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-233">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-233">Int32</span></span>|  
|<span data-ttu-id="d8825-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="d8825-235">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-235">Int32</span></span>|  
|<span data-ttu-id="d8825-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="d8825-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-237">Boolean</span></span>|  
|<span data-ttu-id="d8825-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="d8825-239">String</span><span class="sxs-lookup"><span data-stu-id="d8825-239">String</span></span>|  
|<span data-ttu-id="d8825-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-240">IS_NULLABLE</span></span>|<span data-ttu-id="d8825-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-241">Boolean</span></span>|  
|<span data-ttu-id="d8825-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-242">DATA_TYPE</span></span>|<span data-ttu-id="d8825-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-243">Int32</span></span>|  
|<span data-ttu-id="d8825-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d8825-245">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-245">Int64</span></span>|  
|<span data-ttu-id="d8825-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d8825-247">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-247">Int64</span></span>|  
|<span data-ttu-id="d8825-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d8825-249">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-249">Int32</span></span>|  
|<span data-ttu-id="d8825-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d8825-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="d8825-251">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-251">Int16</span></span>|  
|<span data-ttu-id="d8825-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-252">DESCRIPTION</span></span>|<span data-ttu-id="d8825-253">String</span><span class="sxs-lookup"><span data-stu-id="d8825-253">String</span></span>|  
|<span data-ttu-id="d8825-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-254">TYPE_NAME</span></span>|<span data-ttu-id="d8825-255">String</span><span class="sxs-lookup"><span data-stu-id="d8825-255">String</span></span>|  
|<span data-ttu-id="d8825-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="d8825-257">String</span><span class="sxs-lookup"><span data-stu-id="d8825-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="d8825-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="d8825-258">Catalog</span></span>  
  
|<span data-ttu-id="d8825-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-259">ColumnName</span></span>|<span data-ttu-id="d8825-260">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-261">CATALOG_NAME</span></span>|<span data-ttu-id="d8825-262">String</span><span class="sxs-lookup"><span data-stu-id="d8825-262">String</span></span>|  
|<span data-ttu-id="d8825-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-263">DESCRIPTION</span></span>|<span data-ttu-id="d8825-264">String</span><span class="sxs-lookup"><span data-stu-id="d8825-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d8825-265">Índices</span><span class="sxs-lookup"><span data-stu-id="d8825-265">Indexes</span></span>  
  
|<span data-ttu-id="d8825-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-266">ColumnName</span></span>|<span data-ttu-id="d8825-267">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-268">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-269">String</span><span class="sxs-lookup"><span data-stu-id="d8825-269">String</span></span>|  
|<span data-ttu-id="d8825-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-271">String</span><span class="sxs-lookup"><span data-stu-id="d8825-271">String</span></span>|  
|<span data-ttu-id="d8825-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-272">TABLE_NAME</span></span>|<span data-ttu-id="d8825-273">String</span><span class="sxs-lookup"><span data-stu-id="d8825-273">String</span></span>|  
|<span data-ttu-id="d8825-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-274">INDEX_CATALOG</span></span>|<span data-ttu-id="d8825-275">String</span><span class="sxs-lookup"><span data-stu-id="d8825-275">String</span></span>|  
|<span data-ttu-id="d8825-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="d8825-277">String</span><span class="sxs-lookup"><span data-stu-id="d8825-277">String</span></span>|  
|<span data-ttu-id="d8825-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-278">INDEX_NAME</span></span>|<span data-ttu-id="d8825-279">String</span><span class="sxs-lookup"><span data-stu-id="d8825-279">String</span></span>|  
|<span data-ttu-id="d8825-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d8825-280">PRIMARY_KEY</span></span>|<span data-ttu-id="d8825-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-281">Boolean</span></span>|  
|<span data-ttu-id="d8825-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d8825-282">UNIQUE</span></span>|<span data-ttu-id="d8825-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-283">Boolean</span></span>|  
|<span data-ttu-id="d8825-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d8825-284">CLUSTERED</span></span>|<span data-ttu-id="d8825-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-285">Boolean</span></span>|  
|<span data-ttu-id="d8825-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-286">TYPE</span></span>|<span data-ttu-id="d8825-287">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-287">Int32</span></span>|  
|<span data-ttu-id="d8825-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d8825-288">FILL_FACTOR</span></span>|<span data-ttu-id="d8825-289">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-289">Int32</span></span>|  
|<span data-ttu-id="d8825-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8825-290">INITIAL_SIZE</span></span>|<span data-ttu-id="d8825-291">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-291">Int32</span></span>|  
|<span data-ttu-id="d8825-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="d8825-292">NULLS</span></span>|<span data-ttu-id="d8825-293">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-293">Int32</span></span>|  
|<span data-ttu-id="d8825-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d8825-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d8825-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-295">Boolean</span></span>|  
|<span data-ttu-id="d8825-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d8825-296">AUTO_UPDATE</span></span>|<span data-ttu-id="d8825-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-297">Boolean</span></span>|  
|<span data-ttu-id="d8825-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-298">NULL_COLLATION</span></span>|<span data-ttu-id="d8825-299">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-299">Int32</span></span>|  
|<span data-ttu-id="d8825-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-301">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-301">Int64</span></span>|  
|<span data-ttu-id="d8825-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-302">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-303">String</span><span class="sxs-lookup"><span data-stu-id="d8825-303">String</span></span>|  
|<span data-ttu-id="d8825-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-304">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-305">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-305">Guid</span></span>|  
|<span data-ttu-id="d8825-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-306">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-307">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-307">Int64</span></span>|  
|<span data-ttu-id="d8825-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-308">COLLATION</span></span>|<span data-ttu-id="d8825-309">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-309">Int16</span></span>|  
|<span data-ttu-id="d8825-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d8825-310">CARDINALITY</span></span>|<span data-ttu-id="d8825-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="d8825-311">Decimal</span></span>|  
|<span data-ttu-id="d8825-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="d8825-312">PAGES</span></span>|<span data-ttu-id="d8825-313">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-313">Int32</span></span>|  
|<span data-ttu-id="d8825-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d8825-314">FILTER_CONDITION</span></span>|<span data-ttu-id="d8825-315">String</span><span class="sxs-lookup"><span data-stu-id="d8825-315">String</span></span>|  
|<span data-ttu-id="d8825-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d8825-316">INTEGRATED</span></span>|<span data-ttu-id="d8825-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="d8825-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="d8825-318">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="d8825-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="d8825-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="d8825-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8825-320">Tables</span></span>  
  
- <span data-ttu-id="d8825-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8825-321">Columns</span></span>  
  
- <span data-ttu-id="d8825-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8825-322">Procedures</span></span>  
  
- <span data-ttu-id="d8825-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8825-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="d8825-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d8825-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="d8825-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8825-325">Views</span></span>  
  
- <span data-ttu-id="d8825-326">Índices</span><span class="sxs-lookup"><span data-stu-id="d8825-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d8825-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8825-327">Tables</span></span>  
  
|<span data-ttu-id="d8825-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-328">ColumnName</span></span>|<span data-ttu-id="d8825-329">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-330">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-331">String</span><span class="sxs-lookup"><span data-stu-id="d8825-331">String</span></span>|  
|<span data-ttu-id="d8825-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-333">String</span><span class="sxs-lookup"><span data-stu-id="d8825-333">String</span></span>|  
|<span data-ttu-id="d8825-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-334">TABLE_NAME</span></span>|<span data-ttu-id="d8825-335">String</span><span class="sxs-lookup"><span data-stu-id="d8825-335">String</span></span>|  
|<span data-ttu-id="d8825-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-336">TABLE_TYPE</span></span>|<span data-ttu-id="d8825-337">String</span><span class="sxs-lookup"><span data-stu-id="d8825-337">String</span></span>|  
|<span data-ttu-id="d8825-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-338">TABLE_GUID</span></span>|<span data-ttu-id="d8825-339">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-339">Guid</span></span>|  
|<span data-ttu-id="d8825-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-340">DESCRIPTION</span></span>|<span data-ttu-id="d8825-341">String</span><span class="sxs-lookup"><span data-stu-id="d8825-341">String</span></span>|  
|<span data-ttu-id="d8825-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-342">TABLE_PROPID</span></span>|<span data-ttu-id="d8825-343">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-343">Int64</span></span>|  
|<span data-ttu-id="d8825-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-344">DATE_CREATED</span></span>|<span data-ttu-id="d8825-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-345">DateTime</span></span>|  
|<span data-ttu-id="d8825-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-346">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d8825-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8825-348">Columns</span></span>  
  
|<span data-ttu-id="d8825-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-349">ColumnName</span></span>|<span data-ttu-id="d8825-350">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-351">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-352">String</span><span class="sxs-lookup"><span data-stu-id="d8825-352">String</span></span>|  
|<span data-ttu-id="d8825-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-354">String</span><span class="sxs-lookup"><span data-stu-id="d8825-354">String</span></span>|  
|<span data-ttu-id="d8825-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-355">TABLE_NAME</span></span>|<span data-ttu-id="d8825-356">String</span><span class="sxs-lookup"><span data-stu-id="d8825-356">String</span></span>|  
|<span data-ttu-id="d8825-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-357">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-358">String</span><span class="sxs-lookup"><span data-stu-id="d8825-358">String</span></span>|  
|<span data-ttu-id="d8825-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-359">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-360">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-360">Guid</span></span>|  
|<span data-ttu-id="d8825-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-361">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-362">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-362">Int64</span></span>|  
|<span data-ttu-id="d8825-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-364">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-364">Int64</span></span>|  
|<span data-ttu-id="d8825-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d8825-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-366">Boolean</span></span>|  
|<span data-ttu-id="d8825-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d8825-368">String</span><span class="sxs-lookup"><span data-stu-id="d8825-368">String</span></span>|  
|<span data-ttu-id="d8825-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d8825-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="d8825-370">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-370">Int64</span></span>|  
|<span data-ttu-id="d8825-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-371">IS_NULLABLE</span></span>|<span data-ttu-id="d8825-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-372">Boolean</span></span>|  
|<span data-ttu-id="d8825-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-373">DATA_TYPE</span></span>|<span data-ttu-id="d8825-374">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-374">Int32</span></span>|  
|<span data-ttu-id="d8825-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-375">TYPE_GUID</span></span>|<span data-ttu-id="d8825-376">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-376">Guid</span></span>|  
|<span data-ttu-id="d8825-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d8825-378">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-378">Int64</span></span>|  
|<span data-ttu-id="d8825-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d8825-380">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-380">Int64</span></span>|  
|<span data-ttu-id="d8825-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d8825-382">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-382">Int32</span></span>|  
|<span data-ttu-id="d8825-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d8825-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="d8825-384">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-384">Int16</span></span>|  
|<span data-ttu-id="d8825-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="d8825-386">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-386">Int64</span></span>|  
|<span data-ttu-id="d8825-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d8825-388">String</span><span class="sxs-lookup"><span data-stu-id="d8825-388">String</span></span>|  
|<span data-ttu-id="d8825-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d8825-390">String</span><span class="sxs-lookup"><span data-stu-id="d8825-390">String</span></span>|  
|<span data-ttu-id="d8825-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d8825-392">String</span><span class="sxs-lookup"><span data-stu-id="d8825-392">String</span></span>|  
|<span data-ttu-id="d8825-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="d8825-394">String</span><span class="sxs-lookup"><span data-stu-id="d8825-394">String</span></span>|  
|<span data-ttu-id="d8825-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d8825-396">String</span><span class="sxs-lookup"><span data-stu-id="d8825-396">String</span></span>|  
|<span data-ttu-id="d8825-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-397">COLLATION_NAME</span></span>|<span data-ttu-id="d8825-398">String</span><span class="sxs-lookup"><span data-stu-id="d8825-398">String</span></span>|  
|<span data-ttu-id="d8825-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d8825-400">String</span><span class="sxs-lookup"><span data-stu-id="d8825-400">String</span></span>|  
|<span data-ttu-id="d8825-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d8825-402">String</span><span class="sxs-lookup"><span data-stu-id="d8825-402">String</span></span>|  
|<span data-ttu-id="d8825-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-403">DOMAIN_NAME</span></span>|<span data-ttu-id="d8825-404">String</span><span class="sxs-lookup"><span data-stu-id="d8825-404">String</span></span>|  
|<span data-ttu-id="d8825-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-405">DESCRIPTION</span></span>|<span data-ttu-id="d8825-406">String</span><span class="sxs-lookup"><span data-stu-id="d8825-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d8825-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8825-407">Procedures</span></span>  
  
|<span data-ttu-id="d8825-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-408">ColumnName</span></span>|<span data-ttu-id="d8825-409">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d8825-411">String</span><span class="sxs-lookup"><span data-stu-id="d8825-411">String</span></span>|  
|<span data-ttu-id="d8825-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d8825-413">String</span><span class="sxs-lookup"><span data-stu-id="d8825-413">String</span></span>|  
|<span data-ttu-id="d8825-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8825-415">String</span><span class="sxs-lookup"><span data-stu-id="d8825-415">String</span></span>|  
|<span data-ttu-id="d8825-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d8825-417">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-417">Int16</span></span>|  
|<span data-ttu-id="d8825-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d8825-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d8825-419">String</span><span class="sxs-lookup"><span data-stu-id="d8825-419">String</span></span>|  
|<span data-ttu-id="d8825-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-420">DESCRIPTION</span></span>|<span data-ttu-id="d8825-421">String</span><span class="sxs-lookup"><span data-stu-id="d8825-421">String</span></span>|  
|<span data-ttu-id="d8825-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-422">DATE_CREATED</span></span>|<span data-ttu-id="d8825-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-423">DateTime</span></span>|  
|<span data-ttu-id="d8825-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-424">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d8825-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d8825-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d8825-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-427">ColumnName</span></span>|<span data-ttu-id="d8825-428">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d8825-430">String</span><span class="sxs-lookup"><span data-stu-id="d8825-430">String</span></span>|  
|<span data-ttu-id="d8825-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d8825-432">String</span><span class="sxs-lookup"><span data-stu-id="d8825-432">String</span></span>|  
|<span data-ttu-id="d8825-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8825-434">String</span><span class="sxs-lookup"><span data-stu-id="d8825-434">String</span></span>|  
|<span data-ttu-id="d8825-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-435">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-436">String</span><span class="sxs-lookup"><span data-stu-id="d8825-436">String</span></span>|  
|<span data-ttu-id="d8825-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-437">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-438">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-438">Guid</span></span>|  
|<span data-ttu-id="d8825-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-439">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-440">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-440">Int64</span></span>|  
|<span data-ttu-id="d8825-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="d8825-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="d8825-442">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-442">Int64</span></span>|  
|<span data-ttu-id="d8825-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-444">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-444">Int64</span></span>|  
|<span data-ttu-id="d8825-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-445">IS_NULLABLE</span></span>|<span data-ttu-id="d8825-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-446">Boolean</span></span>|  
|<span data-ttu-id="d8825-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-447">DATA_TYPE</span></span>|<span data-ttu-id="d8825-448">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-448">Int32</span></span>|  
|<span data-ttu-id="d8825-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-449">TYPE_GUID</span></span>|<span data-ttu-id="d8825-450">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-450">Guid</span></span>|  
|<span data-ttu-id="d8825-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d8825-452">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-452">Int64</span></span>|  
|<span data-ttu-id="d8825-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d8825-454">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-454">Int64</span></span>|  
|<span data-ttu-id="d8825-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d8825-456">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-456">Int32</span></span>|  
|<span data-ttu-id="d8825-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d8825-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="d8825-458">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-458">Int16</span></span>|  
|<span data-ttu-id="d8825-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-459">DESCRIPTION</span></span>|<span data-ttu-id="d8825-460">String</span><span class="sxs-lookup"><span data-stu-id="d8825-460">String</span></span>|  
|<span data-ttu-id="d8825-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d8825-461">OVERLOAD</span></span>|<span data-ttu-id="d8825-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d8825-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8825-463">Views</span></span>  
  
|<span data-ttu-id="d8825-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-464">ColumnName</span></span>|<span data-ttu-id="d8825-465">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-466">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-467">String</span><span class="sxs-lookup"><span data-stu-id="d8825-467">String</span></span>|  
|<span data-ttu-id="d8825-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-469">String</span><span class="sxs-lookup"><span data-stu-id="d8825-469">String</span></span>|  
|<span data-ttu-id="d8825-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-470">TABLE_NAME</span></span>|<span data-ttu-id="d8825-471">String</span><span class="sxs-lookup"><span data-stu-id="d8825-471">String</span></span>|  
|<span data-ttu-id="d8825-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d8825-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="d8825-473">String</span><span class="sxs-lookup"><span data-stu-id="d8825-473">String</span></span>|  
|<span data-ttu-id="d8825-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-474">CHECK_OPTION</span></span>|<span data-ttu-id="d8825-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-475">Boolean</span></span>|  
|<span data-ttu-id="d8825-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-476">IS_UPDATABLE</span></span>|<span data-ttu-id="d8825-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-477">Boolean</span></span>|  
|<span data-ttu-id="d8825-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-478">DESCRIPTION</span></span>|<span data-ttu-id="d8825-479">String</span><span class="sxs-lookup"><span data-stu-id="d8825-479">String</span></span>|  
|<span data-ttu-id="d8825-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-480">DATE_CREATED</span></span>|<span data-ttu-id="d8825-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-481">DateTime</span></span>|  
|<span data-ttu-id="d8825-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-482">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d8825-484">Índices</span><span class="sxs-lookup"><span data-stu-id="d8825-484">Indexes</span></span>  
  
|<span data-ttu-id="d8825-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-485">ColumnName</span></span>|<span data-ttu-id="d8825-486">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-487">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-488">String</span><span class="sxs-lookup"><span data-stu-id="d8825-488">String</span></span>|  
|<span data-ttu-id="d8825-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-490">String</span><span class="sxs-lookup"><span data-stu-id="d8825-490">String</span></span>|  
|<span data-ttu-id="d8825-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-491">TABLE_NAME</span></span>|<span data-ttu-id="d8825-492">String</span><span class="sxs-lookup"><span data-stu-id="d8825-492">String</span></span>|  
|<span data-ttu-id="d8825-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-493">INDEX_CATALOG</span></span>|<span data-ttu-id="d8825-494">String</span><span class="sxs-lookup"><span data-stu-id="d8825-494">String</span></span>|  
|<span data-ttu-id="d8825-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="d8825-496">String</span><span class="sxs-lookup"><span data-stu-id="d8825-496">String</span></span>|  
|<span data-ttu-id="d8825-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-497">INDEX_NAME</span></span>|<span data-ttu-id="d8825-498">String</span><span class="sxs-lookup"><span data-stu-id="d8825-498">String</span></span>|  
|<span data-ttu-id="d8825-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d8825-499">PRIMARY_KEY</span></span>|<span data-ttu-id="d8825-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-500">Boolean</span></span>|  
|<span data-ttu-id="d8825-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d8825-501">UNIQUE</span></span>|<span data-ttu-id="d8825-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-502">Boolean</span></span>|  
|<span data-ttu-id="d8825-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d8825-503">CLUSTERED</span></span>|<span data-ttu-id="d8825-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-504">Boolean</span></span>|  
|<span data-ttu-id="d8825-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-505">TYPE</span></span>|<span data-ttu-id="d8825-506">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-506">Int32</span></span>|  
|<span data-ttu-id="d8825-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d8825-507">FILL_FACTOR</span></span>|<span data-ttu-id="d8825-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-508">Int32</span></span>|  
|<span data-ttu-id="d8825-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8825-509">INITIAL_SIZE</span></span>|<span data-ttu-id="d8825-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-510">Int32</span></span>|  
|<span data-ttu-id="d8825-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="d8825-511">NULLS</span></span>|<span data-ttu-id="d8825-512">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-512">Int32</span></span>|  
|<span data-ttu-id="d8825-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d8825-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d8825-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-514">Boolean</span></span>|  
|<span data-ttu-id="d8825-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d8825-515">AUTO_UPDATE</span></span>|<span data-ttu-id="d8825-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-516">Boolean</span></span>|  
|<span data-ttu-id="d8825-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-517">NULL_COLLATION</span></span>|<span data-ttu-id="d8825-518">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-518">Int32</span></span>|  
|<span data-ttu-id="d8825-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-520">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-520">Int64</span></span>|  
|<span data-ttu-id="d8825-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-521">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-522">String</span><span class="sxs-lookup"><span data-stu-id="d8825-522">String</span></span>|  
|<span data-ttu-id="d8825-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-523">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-524">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-524">Guid</span></span>|  
|<span data-ttu-id="d8825-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-525">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-526">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-526">Int64</span></span>|  
|<span data-ttu-id="d8825-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-527">COLLATION</span></span>|<span data-ttu-id="d8825-528">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-528">Int16</span></span>|  
|<span data-ttu-id="d8825-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d8825-529">CARDINALITY</span></span>|<span data-ttu-id="d8825-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="d8825-530">Decimal</span></span>|  
|<span data-ttu-id="d8825-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="d8825-531">PAGES</span></span>|<span data-ttu-id="d8825-532">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-532">Int32</span></span>|  
|<span data-ttu-id="d8825-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d8825-533">FILTER_CONDITION</span></span>|<span data-ttu-id="d8825-534">String</span><span class="sxs-lookup"><span data-stu-id="d8825-534">String</span></span>|  
|<span data-ttu-id="d8825-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d8825-535">INTEGRATED</span></span>|<span data-ttu-id="d8825-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="d8825-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="d8825-537">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="d8825-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="d8825-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="d8825-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8825-539">Tables</span></span>  
  
- <span data-ttu-id="d8825-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8825-540">Columns</span></span>  
  
- <span data-ttu-id="d8825-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8825-541">Procedures</span></span>  
  
- <span data-ttu-id="d8825-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8825-542">Views</span></span>  
  
- <span data-ttu-id="d8825-543">Índices</span><span class="sxs-lookup"><span data-stu-id="d8825-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d8825-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="d8825-544">Tables</span></span>  
  
|<span data-ttu-id="d8825-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-545">ColumnName</span></span>|<span data-ttu-id="d8825-546">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-547">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-548">String</span><span class="sxs-lookup"><span data-stu-id="d8825-548">String</span></span>|  
|<span data-ttu-id="d8825-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-550">String</span><span class="sxs-lookup"><span data-stu-id="d8825-550">String</span></span>|  
|<span data-ttu-id="d8825-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-551">TABLE_NAME</span></span>|<span data-ttu-id="d8825-552">String</span><span class="sxs-lookup"><span data-stu-id="d8825-552">String</span></span>|  
|<span data-ttu-id="d8825-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-553">TABLE_TYPE</span></span>|<span data-ttu-id="d8825-554">String</span><span class="sxs-lookup"><span data-stu-id="d8825-554">String</span></span>|  
|<span data-ttu-id="d8825-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-555">TABLE_GUID</span></span>|<span data-ttu-id="d8825-556">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-556">Guid</span></span>|  
|<span data-ttu-id="d8825-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-557">DESCRIPTION</span></span>|<span data-ttu-id="d8825-558">String</span><span class="sxs-lookup"><span data-stu-id="d8825-558">String</span></span>|  
|<span data-ttu-id="d8825-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-559">TABLE_PROPID</span></span>|<span data-ttu-id="d8825-560">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-560">Int64</span></span>|  
|<span data-ttu-id="d8825-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-561">DATE_CREATED</span></span>|<span data-ttu-id="d8825-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-562">DateTime</span></span>|  
|<span data-ttu-id="d8825-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-563">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d8825-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="d8825-565">Columns</span></span>  
  
|<span data-ttu-id="d8825-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-566">ColumnName</span></span>|<span data-ttu-id="d8825-567">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-568">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-569">String</span><span class="sxs-lookup"><span data-stu-id="d8825-569">String</span></span>|  
|<span data-ttu-id="d8825-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-571">String</span><span class="sxs-lookup"><span data-stu-id="d8825-571">String</span></span>|  
|<span data-ttu-id="d8825-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-572">TABLE_NAME</span></span>|<span data-ttu-id="d8825-573">String</span><span class="sxs-lookup"><span data-stu-id="d8825-573">String</span></span>|  
|<span data-ttu-id="d8825-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-574">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-575">String</span><span class="sxs-lookup"><span data-stu-id="d8825-575">String</span></span>|  
|<span data-ttu-id="d8825-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-576">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-577">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-577">Guid</span></span>|  
|<span data-ttu-id="d8825-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-578">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-579">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-579">Int64</span></span>|  
|<span data-ttu-id="d8825-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-581">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-581">Int64</span></span>|  
|<span data-ttu-id="d8825-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d8825-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-583">Boolean</span></span>|  
|<span data-ttu-id="d8825-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d8825-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d8825-585">String</span><span class="sxs-lookup"><span data-stu-id="d8825-585">String</span></span>|  
|<span data-ttu-id="d8825-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d8825-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="d8825-587">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-587">Int64</span></span>|  
|<span data-ttu-id="d8825-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-588">IS_NULLABLE</span></span>|<span data-ttu-id="d8825-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-589">Boolean</span></span>|  
|<span data-ttu-id="d8825-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-590">DATA_TYPE</span></span>|<span data-ttu-id="d8825-591">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-591">Int32</span></span>|  
|<span data-ttu-id="d8825-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-592">TYPE_GUID</span></span>|<span data-ttu-id="d8825-593">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-593">Guid</span></span>|  
|<span data-ttu-id="d8825-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d8825-595">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-595">Int64</span></span>|  
|<span data-ttu-id="d8825-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d8825-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d8825-597">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-597">Int64</span></span>|  
|<span data-ttu-id="d8825-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d8825-599">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-599">Int32</span></span>|  
|<span data-ttu-id="d8825-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d8825-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="d8825-601">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-601">Int16</span></span>|  
|<span data-ttu-id="d8825-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d8825-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="d8825-603">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-603">Int64</span></span>|  
|<span data-ttu-id="d8825-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d8825-605">String</span><span class="sxs-lookup"><span data-stu-id="d8825-605">String</span></span>|  
|<span data-ttu-id="d8825-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d8825-607">String</span><span class="sxs-lookup"><span data-stu-id="d8825-607">String</span></span>|  
|<span data-ttu-id="d8825-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d8825-609">String</span><span class="sxs-lookup"><span data-stu-id="d8825-609">String</span></span>|  
|<span data-ttu-id="d8825-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="d8825-611">String</span><span class="sxs-lookup"><span data-stu-id="d8825-611">String</span></span>|  
|<span data-ttu-id="d8825-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d8825-613">String</span><span class="sxs-lookup"><span data-stu-id="d8825-613">String</span></span>|  
|<span data-ttu-id="d8825-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-614">COLLATION_NAME</span></span>|<span data-ttu-id="d8825-615">String</span><span class="sxs-lookup"><span data-stu-id="d8825-615">String</span></span>|  
|<span data-ttu-id="d8825-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d8825-617">String</span><span class="sxs-lookup"><span data-stu-id="d8825-617">String</span></span>|  
|<span data-ttu-id="d8825-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d8825-619">String</span><span class="sxs-lookup"><span data-stu-id="d8825-619">String</span></span>|  
|<span data-ttu-id="d8825-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-620">DOMAIN_NAME</span></span>|<span data-ttu-id="d8825-621">String</span><span class="sxs-lookup"><span data-stu-id="d8825-621">String</span></span>|  
|<span data-ttu-id="d8825-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-622">DESCRIPTION</span></span>|<span data-ttu-id="d8825-623">String</span><span class="sxs-lookup"><span data-stu-id="d8825-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d8825-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d8825-624">Procedures</span></span>  
  
|<span data-ttu-id="d8825-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-625">ColumnName</span></span>|<span data-ttu-id="d8825-626">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d8825-628">String</span><span class="sxs-lookup"><span data-stu-id="d8825-628">String</span></span>|  
|<span data-ttu-id="d8825-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d8825-630">String</span><span class="sxs-lookup"><span data-stu-id="d8825-630">String</span></span>|  
|<span data-ttu-id="d8825-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="d8825-632">String</span><span class="sxs-lookup"><span data-stu-id="d8825-632">String</span></span>|  
|<span data-ttu-id="d8825-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d8825-634">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-634">Int16</span></span>|  
|<span data-ttu-id="d8825-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d8825-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d8825-636">String</span><span class="sxs-lookup"><span data-stu-id="d8825-636">String</span></span>|  
|<span data-ttu-id="d8825-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-637">DESCRIPTION</span></span>|<span data-ttu-id="d8825-638">String</span><span class="sxs-lookup"><span data-stu-id="d8825-638">String</span></span>|  
|<span data-ttu-id="d8825-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-639">DATE_CREATED</span></span>|<span data-ttu-id="d8825-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-640">DateTime</span></span>|  
|<span data-ttu-id="d8825-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-641">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d8825-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="d8825-643">Views</span></span>  
  
|<span data-ttu-id="d8825-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-644">ColumnName</span></span>|<span data-ttu-id="d8825-645">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-646">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-647">String</span><span class="sxs-lookup"><span data-stu-id="d8825-647">String</span></span>|  
|<span data-ttu-id="d8825-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-649">String</span><span class="sxs-lookup"><span data-stu-id="d8825-649">String</span></span>|  
|<span data-ttu-id="d8825-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-650">TABLE_NAME</span></span>|<span data-ttu-id="d8825-651">String</span><span class="sxs-lookup"><span data-stu-id="d8825-651">String</span></span>|  
|<span data-ttu-id="d8825-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d8825-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="d8825-653">String</span><span class="sxs-lookup"><span data-stu-id="d8825-653">String</span></span>|  
|<span data-ttu-id="d8825-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-654">CHECK_OPTION</span></span>|<span data-ttu-id="d8825-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-655">Boolean</span></span>|  
|<span data-ttu-id="d8825-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d8825-656">IS_UPDATABLE</span></span>|<span data-ttu-id="d8825-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-657">Boolean</span></span>|  
|<span data-ttu-id="d8825-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8825-658">DESCRIPTION</span></span>|<span data-ttu-id="d8825-659">String</span><span class="sxs-lookup"><span data-stu-id="d8825-659">String</span></span>|  
|<span data-ttu-id="d8825-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d8825-660">DATE_CREATED</span></span>|<span data-ttu-id="d8825-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-661">DateTime</span></span>|  
|<span data-ttu-id="d8825-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d8825-662">DATE_MODIFIED</span></span>|<span data-ttu-id="d8825-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="d8825-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d8825-664">Índices</span><span class="sxs-lookup"><span data-stu-id="d8825-664">Indexes</span></span>  
  
|<span data-ttu-id="d8825-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d8825-665">ColumnName</span></span>|<span data-ttu-id="d8825-666">DataType</span><span class="sxs-lookup"><span data-stu-id="d8825-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d8825-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-667">TABLE_CATALOG</span></span>|<span data-ttu-id="d8825-668">String</span><span class="sxs-lookup"><span data-stu-id="d8825-668">String</span></span>|  
|<span data-ttu-id="d8825-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="d8825-670">String</span><span class="sxs-lookup"><span data-stu-id="d8825-670">String</span></span>|  
|<span data-ttu-id="d8825-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-671">TABLE_NAME</span></span>|<span data-ttu-id="d8825-672">String</span><span class="sxs-lookup"><span data-stu-id="d8825-672">String</span></span>|  
|<span data-ttu-id="d8825-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d8825-673">INDEX_CATALOG</span></span>|<span data-ttu-id="d8825-674">String</span><span class="sxs-lookup"><span data-stu-id="d8825-674">String</span></span>|  
|<span data-ttu-id="d8825-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d8825-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="d8825-676">String</span><span class="sxs-lookup"><span data-stu-id="d8825-676">String</span></span>|  
|<span data-ttu-id="d8825-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-677">INDEX_NAME</span></span>|<span data-ttu-id="d8825-678">String</span><span class="sxs-lookup"><span data-stu-id="d8825-678">String</span></span>|  
|<span data-ttu-id="d8825-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d8825-679">PRIMARY_KEY</span></span>|<span data-ttu-id="d8825-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-680">Boolean</span></span>|  
|<span data-ttu-id="d8825-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d8825-681">UNIQUE</span></span>|<span data-ttu-id="d8825-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-682">Boolean</span></span>|  
|<span data-ttu-id="d8825-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d8825-683">CLUSTERED</span></span>|<span data-ttu-id="d8825-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-684">Boolean</span></span>|  
|<span data-ttu-id="d8825-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="d8825-685">TYPE</span></span>|<span data-ttu-id="d8825-686">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-686">Int32</span></span>|  
|<span data-ttu-id="d8825-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d8825-687">FILL_FACTOR</span></span>|<span data-ttu-id="d8825-688">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-688">Int32</span></span>|  
|<span data-ttu-id="d8825-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d8825-689">INITIAL_SIZE</span></span>|<span data-ttu-id="d8825-690">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-690">Int32</span></span>|  
|<span data-ttu-id="d8825-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="d8825-691">NULLS</span></span>|<span data-ttu-id="d8825-692">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-692">Int32</span></span>|  
|<span data-ttu-id="d8825-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d8825-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d8825-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-694">Boolean</span></span>|  
|<span data-ttu-id="d8825-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d8825-695">AUTO_UPDATE</span></span>|<span data-ttu-id="d8825-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-696">Boolean</span></span>|  
|<span data-ttu-id="d8825-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-697">NULL_COLLATION</span></span>|<span data-ttu-id="d8825-698">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-698">Int32</span></span>|  
|<span data-ttu-id="d8825-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d8825-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="d8825-700">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-700">Int64</span></span>|  
|<span data-ttu-id="d8825-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d8825-701">COLUMN_NAME</span></span>|<span data-ttu-id="d8825-702">String</span><span class="sxs-lookup"><span data-stu-id="d8825-702">String</span></span>|  
|<span data-ttu-id="d8825-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d8825-703">COLUMN_GUID</span></span>|<span data-ttu-id="d8825-704">Guid</span><span class="sxs-lookup"><span data-stu-id="d8825-704">Guid</span></span>|  
|<span data-ttu-id="d8825-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d8825-705">COLUMN_PROPID</span></span>|<span data-ttu-id="d8825-706">Int64</span><span class="sxs-lookup"><span data-stu-id="d8825-706">Int64</span></span>|  
|<span data-ttu-id="d8825-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d8825-707">COLLATION</span></span>|<span data-ttu-id="d8825-708">Int16</span><span class="sxs-lookup"><span data-stu-id="d8825-708">Int16</span></span>|  
|<span data-ttu-id="d8825-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d8825-709">CARDINALITY</span></span>|<span data-ttu-id="d8825-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="d8825-710">Decimal</span></span>|  
|<span data-ttu-id="d8825-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="d8825-711">PAGES</span></span>|<span data-ttu-id="d8825-712">Int32</span><span class="sxs-lookup"><span data-stu-id="d8825-712">Int32</span></span>|  
|<span data-ttu-id="d8825-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d8825-713">FILTER_CONDITION</span></span>|<span data-ttu-id="d8825-714">String</span><span class="sxs-lookup"><span data-stu-id="d8825-714">String</span></span>|  
|<span data-ttu-id="d8825-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d8825-715">INTEGRATED</span></span>|<span data-ttu-id="d8825-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="d8825-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8825-717">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8825-717">See also</span></span>

- [<span data-ttu-id="d8825-718">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d8825-718">ADO.NET Overview</span></span>](ado-net-overview.md)

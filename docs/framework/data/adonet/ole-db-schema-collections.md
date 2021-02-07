---
description: 'Más información acerca de: OLE DB de las colecciones de esquemas'
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: d4d4bae5387575bdaeaf013ed690e95aa3259068
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672626"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="0c696-103">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="0c696-103">OLE DB Schema Collections</span></span>

<span data-ttu-id="0c696-104">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="0c696-104">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="0c696-105">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c696-105">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="0c696-106">El controlador OLE DB de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="0c696-106">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="0c696-107">Tablas</span><span class="sxs-lookup"><span data-stu-id="0c696-107">Tables</span></span>  
  
- <span data-ttu-id="0c696-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="0c696-108">Columns</span></span>  
  
- <span data-ttu-id="0c696-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c696-109">Procedures</span></span>  
  
- <span data-ttu-id="0c696-110">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0c696-110">ProcedureParameters</span></span>  
  
- <span data-ttu-id="0c696-111">Catálogo</span><span class="sxs-lookup"><span data-stu-id="0c696-111">Catalog</span></span>  
  
- <span data-ttu-id="0c696-112">Índices</span><span class="sxs-lookup"><span data-stu-id="0c696-112">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0c696-113">Tablas</span><span class="sxs-lookup"><span data-stu-id="0c696-113">Tables</span></span>  
  
|<span data-ttu-id="0c696-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-114">ColumnName</span></span>|<span data-ttu-id="0c696-115">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-116">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-117">String</span><span class="sxs-lookup"><span data-stu-id="0c696-117">String</span></span>|  
|<span data-ttu-id="0c696-118">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-118">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-119">String</span><span class="sxs-lookup"><span data-stu-id="0c696-119">String</span></span>|  
|<span data-ttu-id="0c696-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-120">TABLE_NAME</span></span>|<span data-ttu-id="0c696-121">String</span><span class="sxs-lookup"><span data-stu-id="0c696-121">String</span></span>|  
|<span data-ttu-id="0c696-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-122">TABLE_TYPE</span></span>|<span data-ttu-id="0c696-123">String</span><span class="sxs-lookup"><span data-stu-id="0c696-123">String</span></span>|  
|<span data-ttu-id="0c696-124">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-124">TABLE_GUID</span></span>|<span data-ttu-id="0c696-125">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-125">Guid</span></span>|  
|<span data-ttu-id="0c696-126">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-126">DESCRIPTION</span></span>|<span data-ttu-id="0c696-127">String</span><span class="sxs-lookup"><span data-stu-id="0c696-127">String</span></span>|  
|<span data-ttu-id="0c696-128">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-128">TABLE_PROPID</span></span>|<span data-ttu-id="0c696-129">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-129">Int64</span></span>|  
|<span data-ttu-id="0c696-130">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-130">DATE_CREATED</span></span>|<span data-ttu-id="0c696-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-131">DateTime</span></span>|  
|<span data-ttu-id="0c696-132">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-132">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-133">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-133">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0c696-134">Columnas</span><span class="sxs-lookup"><span data-stu-id="0c696-134">Columns</span></span>  
  
|<span data-ttu-id="0c696-135">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-135">ColumnName</span></span>|<span data-ttu-id="0c696-136">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-136">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-137">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-137">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-138">String</span><span class="sxs-lookup"><span data-stu-id="0c696-138">String</span></span>|  
|<span data-ttu-id="0c696-139">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-139">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-140">String</span><span class="sxs-lookup"><span data-stu-id="0c696-140">String</span></span>|  
|<span data-ttu-id="0c696-141">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-141">TABLE_NAME</span></span>|<span data-ttu-id="0c696-142">String</span><span class="sxs-lookup"><span data-stu-id="0c696-142">String</span></span>|  
|<span data-ttu-id="0c696-143">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-143">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-144">String</span><span class="sxs-lookup"><span data-stu-id="0c696-144">String</span></span>|  
|<span data-ttu-id="0c696-145">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-145">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-146">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-146">Guid</span></span>|  
|<span data-ttu-id="0c696-147">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-147">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-148">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-148">Int64</span></span>|  
|<span data-ttu-id="0c696-149">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-149">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-150">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-150">Int64</span></span>|  
|<span data-ttu-id="0c696-151">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-151">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0c696-152">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-152">Boolean</span></span>|  
|<span data-ttu-id="0c696-153">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-153">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0c696-154">String</span><span class="sxs-lookup"><span data-stu-id="0c696-154">String</span></span>|  
|<span data-ttu-id="0c696-155">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0c696-155">COLUMN_FLAGS</span></span>|<span data-ttu-id="0c696-156">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-156">Int64</span></span>|  
|<span data-ttu-id="0c696-157">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-157">IS_NULLABLE</span></span>|<span data-ttu-id="0c696-158">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-158">Boolean</span></span>|  
|<span data-ttu-id="0c696-159">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-159">DATA_TYPE</span></span>|<span data-ttu-id="0c696-160">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-160">Int32</span></span>|  
|<span data-ttu-id="0c696-161">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-161">TYPE_GUID</span></span>|<span data-ttu-id="0c696-162">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-162">Guid</span></span>|  
|<span data-ttu-id="0c696-163">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-163">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0c696-164">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-164">Int64</span></span>|  
|<span data-ttu-id="0c696-165">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-165">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0c696-166">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-166">Int64</span></span>|  
|<span data-ttu-id="0c696-167">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-167">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0c696-168">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-168">Int32</span></span>|  
|<span data-ttu-id="0c696-169">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0c696-169">NUMERIC_SCALE</span></span>|<span data-ttu-id="0c696-170">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-170">Int16</span></span>|  
|<span data-ttu-id="0c696-171">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-171">DATETIME_PRECISION</span></span>|<span data-ttu-id="0c696-172">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-172">Int64</span></span>|  
|<span data-ttu-id="0c696-173">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-173">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0c696-174">String</span><span class="sxs-lookup"><span data-stu-id="0c696-174">String</span></span>|  
|<span data-ttu-id="0c696-175">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-175">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0c696-176">String</span><span class="sxs-lookup"><span data-stu-id="0c696-176">String</span></span>|  
|<span data-ttu-id="0c696-177">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-177">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0c696-178">String</span><span class="sxs-lookup"><span data-stu-id="0c696-178">String</span></span>|  
|<span data-ttu-id="0c696-179">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-179">COLLATION_CATALOG</span></span>|<span data-ttu-id="0c696-180">String</span><span class="sxs-lookup"><span data-stu-id="0c696-180">String</span></span>|  
|<span data-ttu-id="0c696-181">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-181">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0c696-182">String</span><span class="sxs-lookup"><span data-stu-id="0c696-182">String</span></span>|  
|<span data-ttu-id="0c696-183">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-183">COLLATION_NAME</span></span>|<span data-ttu-id="0c696-184">String</span><span class="sxs-lookup"><span data-stu-id="0c696-184">String</span></span>|  
|<span data-ttu-id="0c696-185">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-185">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0c696-186">String</span><span class="sxs-lookup"><span data-stu-id="0c696-186">String</span></span>|  
|<span data-ttu-id="0c696-187">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-187">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0c696-188">String</span><span class="sxs-lookup"><span data-stu-id="0c696-188">String</span></span>|  
|<span data-ttu-id="0c696-189">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-189">DOMAIN_NAME</span></span>|<span data-ttu-id="0c696-190">String</span><span class="sxs-lookup"><span data-stu-id="0c696-190">String</span></span>|  
|<span data-ttu-id="0c696-191">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-191">DESCRIPTION</span></span>|<span data-ttu-id="0c696-192">String</span><span class="sxs-lookup"><span data-stu-id="0c696-192">String</span></span>|  
|<span data-ttu-id="0c696-193">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="0c696-193">COLUMN_LCID</span></span>|<span data-ttu-id="0c696-194">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-194">Int32</span></span>|  
|<span data-ttu-id="0c696-195">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="0c696-195">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="0c696-196">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-196">Int32</span></span>|  
|<span data-ttu-id="0c696-197">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="0c696-197">COLUMN_SORTID</span></span>|<span data-ttu-id="0c696-198">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-198">Int32</span></span>|  
|<span data-ttu-id="0c696-199">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-199">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="0c696-200">Byte[]</span><span class="sxs-lookup"><span data-stu-id="0c696-200">Byte[]</span></span>|  
|<span data-ttu-id="0c696-201">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="0c696-201">IS_COMPUTED</span></span>|<span data-ttu-id="0c696-202">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-202">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0c696-203">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c696-203">Procedures</span></span>  
  
|<span data-ttu-id="0c696-204">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-204">ColumnName</span></span>|<span data-ttu-id="0c696-205">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-205">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-206">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-206">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0c696-207">String</span><span class="sxs-lookup"><span data-stu-id="0c696-207">String</span></span>|  
|<span data-ttu-id="0c696-208">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-208">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0c696-209">String</span><span class="sxs-lookup"><span data-stu-id="0c696-209">String</span></span>|  
|<span data-ttu-id="0c696-210">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-210">PROCEDURE_NAME</span></span>|<span data-ttu-id="0c696-211">String</span><span class="sxs-lookup"><span data-stu-id="0c696-211">String</span></span>|  
|<span data-ttu-id="0c696-212">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-212">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0c696-213">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-213">Int16</span></span>|  
|<span data-ttu-id="0c696-214">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0c696-214">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0c696-215">String</span><span class="sxs-lookup"><span data-stu-id="0c696-215">String</span></span>|  
|<span data-ttu-id="0c696-216">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-216">DESCRIPTION</span></span>|<span data-ttu-id="0c696-217">String</span><span class="sxs-lookup"><span data-stu-id="0c696-217">String</span></span>|  
|<span data-ttu-id="0c696-218">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-218">DATE_CREATED</span></span>|<span data-ttu-id="0c696-219">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-219">DateTime</span></span>|  
|<span data-ttu-id="0c696-220">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-220">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-221">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-221">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0c696-222">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0c696-222">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0c696-223">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-223">ColumnName</span></span>|<span data-ttu-id="0c696-224">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-224">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-225">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-225">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0c696-226">String</span><span class="sxs-lookup"><span data-stu-id="0c696-226">String</span></span>|  
|<span data-ttu-id="0c696-227">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-227">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0c696-228">String</span><span class="sxs-lookup"><span data-stu-id="0c696-228">String</span></span>|  
|<span data-ttu-id="0c696-229">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-229">PROCEDURE_NAME</span></span>|<span data-ttu-id="0c696-230">String</span><span class="sxs-lookup"><span data-stu-id="0c696-230">String</span></span>|  
|<span data-ttu-id="0c696-231">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-231">PARAMETER_NAME</span></span>|<span data-ttu-id="0c696-232">String</span><span class="sxs-lookup"><span data-stu-id="0c696-232">String</span></span>|  
|<span data-ttu-id="0c696-233">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-233">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-234">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-234">Int32</span></span>|  
|<span data-ttu-id="0c696-235">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-235">PARAMETER_TYPE</span></span>|<span data-ttu-id="0c696-236">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-236">Int32</span></span>|  
|<span data-ttu-id="0c696-237">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-237">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="0c696-238">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-238">Boolean</span></span>|  
|<span data-ttu-id="0c696-239">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-239">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="0c696-240">String</span><span class="sxs-lookup"><span data-stu-id="0c696-240">String</span></span>|  
|<span data-ttu-id="0c696-241">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-241">IS_NULLABLE</span></span>|<span data-ttu-id="0c696-242">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-242">Boolean</span></span>|  
|<span data-ttu-id="0c696-243">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-243">DATA_TYPE</span></span>|<span data-ttu-id="0c696-244">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-244">Int32</span></span>|  
|<span data-ttu-id="0c696-245">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-245">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0c696-246">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-246">Int64</span></span>|  
|<span data-ttu-id="0c696-247">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-247">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0c696-248">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-248">Int64</span></span>|  
|<span data-ttu-id="0c696-249">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-249">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0c696-250">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-250">Int32</span></span>|  
|<span data-ttu-id="0c696-251">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0c696-251">NUMERIC_SCALE</span></span>|<span data-ttu-id="0c696-252">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-252">Int16</span></span>|  
|<span data-ttu-id="0c696-253">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-253">DESCRIPTION</span></span>|<span data-ttu-id="0c696-254">String</span><span class="sxs-lookup"><span data-stu-id="0c696-254">String</span></span>|  
|<span data-ttu-id="0c696-255">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-255">TYPE_NAME</span></span>|<span data-ttu-id="0c696-256">String</span><span class="sxs-lookup"><span data-stu-id="0c696-256">String</span></span>|  
|<span data-ttu-id="0c696-257">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-257">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="0c696-258">String</span><span class="sxs-lookup"><span data-stu-id="0c696-258">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="0c696-259">Catálogo</span><span class="sxs-lookup"><span data-stu-id="0c696-259">Catalog</span></span>  
  
|<span data-ttu-id="0c696-260">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-260">ColumnName</span></span>|<span data-ttu-id="0c696-261">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-261">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-262">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-262">CATALOG_NAME</span></span>|<span data-ttu-id="0c696-263">String</span><span class="sxs-lookup"><span data-stu-id="0c696-263">String</span></span>|  
|<span data-ttu-id="0c696-264">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-264">DESCRIPTION</span></span>|<span data-ttu-id="0c696-265">String</span><span class="sxs-lookup"><span data-stu-id="0c696-265">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0c696-266">Índices</span><span class="sxs-lookup"><span data-stu-id="0c696-266">Indexes</span></span>  
  
|<span data-ttu-id="0c696-267">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-267">ColumnName</span></span>|<span data-ttu-id="0c696-268">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-268">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-269">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-269">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-270">String</span><span class="sxs-lookup"><span data-stu-id="0c696-270">String</span></span>|  
|<span data-ttu-id="0c696-271">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-271">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-272">String</span><span class="sxs-lookup"><span data-stu-id="0c696-272">String</span></span>|  
|<span data-ttu-id="0c696-273">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-273">TABLE_NAME</span></span>|<span data-ttu-id="0c696-274">String</span><span class="sxs-lookup"><span data-stu-id="0c696-274">String</span></span>|  
|<span data-ttu-id="0c696-275">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-275">INDEX_CATALOG</span></span>|<span data-ttu-id="0c696-276">String</span><span class="sxs-lookup"><span data-stu-id="0c696-276">String</span></span>|  
|<span data-ttu-id="0c696-277">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-277">INDEX_SCHEMA</span></span>|<span data-ttu-id="0c696-278">String</span><span class="sxs-lookup"><span data-stu-id="0c696-278">String</span></span>|  
|<span data-ttu-id="0c696-279">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-279">INDEX_NAME</span></span>|<span data-ttu-id="0c696-280">String</span><span class="sxs-lookup"><span data-stu-id="0c696-280">String</span></span>|  
|<span data-ttu-id="0c696-281">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0c696-281">PRIMARY_KEY</span></span>|<span data-ttu-id="0c696-282">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-282">Boolean</span></span>|  
|<span data-ttu-id="0c696-283">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0c696-283">UNIQUE</span></span>|<span data-ttu-id="0c696-284">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-284">Boolean</span></span>|  
|<span data-ttu-id="0c696-285">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0c696-285">CLUSTERED</span></span>|<span data-ttu-id="0c696-286">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-286">Boolean</span></span>|  
|<span data-ttu-id="0c696-287">TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-287">TYPE</span></span>|<span data-ttu-id="0c696-288">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-288">Int32</span></span>|  
|<span data-ttu-id="0c696-289">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0c696-289">FILL_FACTOR</span></span>|<span data-ttu-id="0c696-290">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-290">Int32</span></span>|  
|<span data-ttu-id="0c696-291">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0c696-291">INITIAL_SIZE</span></span>|<span data-ttu-id="0c696-292">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-292">Int32</span></span>|  
|<span data-ttu-id="0c696-293">NULLS</span><span class="sxs-lookup"><span data-stu-id="0c696-293">NULLS</span></span>|<span data-ttu-id="0c696-294">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-294">Int32</span></span>|  
|<span data-ttu-id="0c696-295">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0c696-295">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0c696-296">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-296">Boolean</span></span>|  
|<span data-ttu-id="0c696-297">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0c696-297">AUTO_UPDATE</span></span>|<span data-ttu-id="0c696-298">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-298">Boolean</span></span>|  
|<span data-ttu-id="0c696-299">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-299">NULL_COLLATION</span></span>|<span data-ttu-id="0c696-300">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-300">Int32</span></span>|  
|<span data-ttu-id="0c696-301">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-301">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-302">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-302">Int64</span></span>|  
|<span data-ttu-id="0c696-303">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-303">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-304">String</span><span class="sxs-lookup"><span data-stu-id="0c696-304">String</span></span>|  
|<span data-ttu-id="0c696-305">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-305">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-306">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-306">Guid</span></span>|  
|<span data-ttu-id="0c696-307">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-307">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-308">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-308">Int64</span></span>|  
|<span data-ttu-id="0c696-309">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-309">COLLATION</span></span>|<span data-ttu-id="0c696-310">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-310">Int16</span></span>|  
|<span data-ttu-id="0c696-311">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0c696-311">CARDINALITY</span></span>|<span data-ttu-id="0c696-312">Decimal</span><span class="sxs-lookup"><span data-stu-id="0c696-312">Decimal</span></span>|  
|<span data-ttu-id="0c696-313">PAGES</span><span class="sxs-lookup"><span data-stu-id="0c696-313">PAGES</span></span>|<span data-ttu-id="0c696-314">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-314">Int32</span></span>|  
|<span data-ttu-id="0c696-315">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0c696-315">FILTER_CONDITION</span></span>|<span data-ttu-id="0c696-316">String</span><span class="sxs-lookup"><span data-stu-id="0c696-316">String</span></span>|  
|<span data-ttu-id="0c696-317">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0c696-317">INTEGRATED</span></span>|<span data-ttu-id="0c696-318">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-318">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="0c696-319">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="0c696-319">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="0c696-320">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="0c696-320">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="0c696-321">Tablas</span><span class="sxs-lookup"><span data-stu-id="0c696-321">Tables</span></span>  
  
- <span data-ttu-id="0c696-322">Columnas</span><span class="sxs-lookup"><span data-stu-id="0c696-322">Columns</span></span>  
  
- <span data-ttu-id="0c696-323">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c696-323">Procedures</span></span>  
  
- <span data-ttu-id="0c696-324">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0c696-324">ProcedureColumns</span></span>  
  
- <span data-ttu-id="0c696-325">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0c696-325">ProcedureParameters</span></span>  
  
- <span data-ttu-id="0c696-326">Vistas</span><span class="sxs-lookup"><span data-stu-id="0c696-326">Views</span></span>  
  
- <span data-ttu-id="0c696-327">Índices</span><span class="sxs-lookup"><span data-stu-id="0c696-327">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0c696-328">Tablas</span><span class="sxs-lookup"><span data-stu-id="0c696-328">Tables</span></span>  
  
|<span data-ttu-id="0c696-329">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-329">ColumnName</span></span>|<span data-ttu-id="0c696-330">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-330">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-331">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-331">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-332">String</span><span class="sxs-lookup"><span data-stu-id="0c696-332">String</span></span>|  
|<span data-ttu-id="0c696-333">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-333">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-334">String</span><span class="sxs-lookup"><span data-stu-id="0c696-334">String</span></span>|  
|<span data-ttu-id="0c696-335">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-335">TABLE_NAME</span></span>|<span data-ttu-id="0c696-336">String</span><span class="sxs-lookup"><span data-stu-id="0c696-336">String</span></span>|  
|<span data-ttu-id="0c696-337">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-337">TABLE_TYPE</span></span>|<span data-ttu-id="0c696-338">String</span><span class="sxs-lookup"><span data-stu-id="0c696-338">String</span></span>|  
|<span data-ttu-id="0c696-339">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-339">TABLE_GUID</span></span>|<span data-ttu-id="0c696-340">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-340">Guid</span></span>|  
|<span data-ttu-id="0c696-341">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-341">DESCRIPTION</span></span>|<span data-ttu-id="0c696-342">String</span><span class="sxs-lookup"><span data-stu-id="0c696-342">String</span></span>|  
|<span data-ttu-id="0c696-343">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-343">TABLE_PROPID</span></span>|<span data-ttu-id="0c696-344">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-344">Int64</span></span>|  
|<span data-ttu-id="0c696-345">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-345">DATE_CREATED</span></span>|<span data-ttu-id="0c696-346">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-346">DateTime</span></span>|  
|<span data-ttu-id="0c696-347">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-347">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-348">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-348">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0c696-349">Columnas</span><span class="sxs-lookup"><span data-stu-id="0c696-349">Columns</span></span>  
  
|<span data-ttu-id="0c696-350">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-350">ColumnName</span></span>|<span data-ttu-id="0c696-351">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-351">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-352">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-352">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-353">String</span><span class="sxs-lookup"><span data-stu-id="0c696-353">String</span></span>|  
|<span data-ttu-id="0c696-354">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-354">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-355">String</span><span class="sxs-lookup"><span data-stu-id="0c696-355">String</span></span>|  
|<span data-ttu-id="0c696-356">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-356">TABLE_NAME</span></span>|<span data-ttu-id="0c696-357">String</span><span class="sxs-lookup"><span data-stu-id="0c696-357">String</span></span>|  
|<span data-ttu-id="0c696-358">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-358">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-359">String</span><span class="sxs-lookup"><span data-stu-id="0c696-359">String</span></span>|  
|<span data-ttu-id="0c696-360">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-360">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-361">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-361">Guid</span></span>|  
|<span data-ttu-id="0c696-362">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-362">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-363">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-363">Int64</span></span>|  
|<span data-ttu-id="0c696-364">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-364">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-365">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-365">Int64</span></span>|  
|<span data-ttu-id="0c696-366">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-366">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0c696-367">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-367">Boolean</span></span>|  
|<span data-ttu-id="0c696-368">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-368">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0c696-369">String</span><span class="sxs-lookup"><span data-stu-id="0c696-369">String</span></span>|  
|<span data-ttu-id="0c696-370">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0c696-370">COLUMN_FLAGS</span></span>|<span data-ttu-id="0c696-371">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-371">Int64</span></span>|  
|<span data-ttu-id="0c696-372">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-372">IS_NULLABLE</span></span>|<span data-ttu-id="0c696-373">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-373">Boolean</span></span>|  
|<span data-ttu-id="0c696-374">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-374">DATA_TYPE</span></span>|<span data-ttu-id="0c696-375">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-375">Int32</span></span>|  
|<span data-ttu-id="0c696-376">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-376">TYPE_GUID</span></span>|<span data-ttu-id="0c696-377">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-377">Guid</span></span>|  
|<span data-ttu-id="0c696-378">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-378">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0c696-379">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-379">Int64</span></span>|  
|<span data-ttu-id="0c696-380">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-380">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0c696-381">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-381">Int64</span></span>|  
|<span data-ttu-id="0c696-382">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-382">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0c696-383">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-383">Int32</span></span>|  
|<span data-ttu-id="0c696-384">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0c696-384">NUMERIC_SCALE</span></span>|<span data-ttu-id="0c696-385">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-385">Int16</span></span>|  
|<span data-ttu-id="0c696-386">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-386">DATETIME_PRECISION</span></span>|<span data-ttu-id="0c696-387">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-387">Int64</span></span>|  
|<span data-ttu-id="0c696-388">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-388">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0c696-389">String</span><span class="sxs-lookup"><span data-stu-id="0c696-389">String</span></span>|  
|<span data-ttu-id="0c696-390">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-390">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0c696-391">String</span><span class="sxs-lookup"><span data-stu-id="0c696-391">String</span></span>|  
|<span data-ttu-id="0c696-392">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-392">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0c696-393">String</span><span class="sxs-lookup"><span data-stu-id="0c696-393">String</span></span>|  
|<span data-ttu-id="0c696-394">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-394">COLLATION_CATALOG</span></span>|<span data-ttu-id="0c696-395">String</span><span class="sxs-lookup"><span data-stu-id="0c696-395">String</span></span>|  
|<span data-ttu-id="0c696-396">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-396">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0c696-397">String</span><span class="sxs-lookup"><span data-stu-id="0c696-397">String</span></span>|  
|<span data-ttu-id="0c696-398">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-398">COLLATION_NAME</span></span>|<span data-ttu-id="0c696-399">String</span><span class="sxs-lookup"><span data-stu-id="0c696-399">String</span></span>|  
|<span data-ttu-id="0c696-400">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-400">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0c696-401">String</span><span class="sxs-lookup"><span data-stu-id="0c696-401">String</span></span>|  
|<span data-ttu-id="0c696-402">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-402">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0c696-403">String</span><span class="sxs-lookup"><span data-stu-id="0c696-403">String</span></span>|  
|<span data-ttu-id="0c696-404">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-404">DOMAIN_NAME</span></span>|<span data-ttu-id="0c696-405">String</span><span class="sxs-lookup"><span data-stu-id="0c696-405">String</span></span>|  
|<span data-ttu-id="0c696-406">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-406">DESCRIPTION</span></span>|<span data-ttu-id="0c696-407">String</span><span class="sxs-lookup"><span data-stu-id="0c696-407">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0c696-408">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c696-408">Procedures</span></span>  
  
|<span data-ttu-id="0c696-409">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-409">ColumnName</span></span>|<span data-ttu-id="0c696-410">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-410">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-411">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-411">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0c696-412">String</span><span class="sxs-lookup"><span data-stu-id="0c696-412">String</span></span>|  
|<span data-ttu-id="0c696-413">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-413">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0c696-414">String</span><span class="sxs-lookup"><span data-stu-id="0c696-414">String</span></span>|  
|<span data-ttu-id="0c696-415">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-415">PROCEDURE_NAME</span></span>|<span data-ttu-id="0c696-416">String</span><span class="sxs-lookup"><span data-stu-id="0c696-416">String</span></span>|  
|<span data-ttu-id="0c696-417">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-417">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0c696-418">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-418">Int16</span></span>|  
|<span data-ttu-id="0c696-419">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0c696-419">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0c696-420">String</span><span class="sxs-lookup"><span data-stu-id="0c696-420">String</span></span>|  
|<span data-ttu-id="0c696-421">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-421">DESCRIPTION</span></span>|<span data-ttu-id="0c696-422">String</span><span class="sxs-lookup"><span data-stu-id="0c696-422">String</span></span>|  
|<span data-ttu-id="0c696-423">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-423">DATE_CREATED</span></span>|<span data-ttu-id="0c696-424">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-424">DateTime</span></span>|  
|<span data-ttu-id="0c696-425">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-425">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-426">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-426">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0c696-427">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0c696-427">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0c696-428">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-428">ColumnName</span></span>|<span data-ttu-id="0c696-429">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-429">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-430">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-430">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0c696-431">String</span><span class="sxs-lookup"><span data-stu-id="0c696-431">String</span></span>|  
|<span data-ttu-id="0c696-432">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-432">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0c696-433">String</span><span class="sxs-lookup"><span data-stu-id="0c696-433">String</span></span>|  
|<span data-ttu-id="0c696-434">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-434">PROCEDURE_NAME</span></span>|<span data-ttu-id="0c696-435">String</span><span class="sxs-lookup"><span data-stu-id="0c696-435">String</span></span>|  
|<span data-ttu-id="0c696-436">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-436">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-437">String</span><span class="sxs-lookup"><span data-stu-id="0c696-437">String</span></span>|  
|<span data-ttu-id="0c696-438">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-438">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-439">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-439">Guid</span></span>|  
|<span data-ttu-id="0c696-440">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-440">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-441">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-441">Int64</span></span>|  
|<span data-ttu-id="0c696-442">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="0c696-442">ROWSET_NUMBER</span></span>|<span data-ttu-id="0c696-443">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-443">Int64</span></span>|  
|<span data-ttu-id="0c696-444">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-444">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-445">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-445">Int64</span></span>|  
|<span data-ttu-id="0c696-446">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-446">IS_NULLABLE</span></span>|<span data-ttu-id="0c696-447">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-447">Boolean</span></span>|  
|<span data-ttu-id="0c696-448">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-448">DATA_TYPE</span></span>|<span data-ttu-id="0c696-449">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-449">Int32</span></span>|  
|<span data-ttu-id="0c696-450">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-450">TYPE_GUID</span></span>|<span data-ttu-id="0c696-451">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-451">Guid</span></span>|  
|<span data-ttu-id="0c696-452">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-452">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0c696-453">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-453">Int64</span></span>|  
|<span data-ttu-id="0c696-454">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-454">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0c696-455">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-455">Int64</span></span>|  
|<span data-ttu-id="0c696-456">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-456">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0c696-457">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-457">Int32</span></span>|  
|<span data-ttu-id="0c696-458">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0c696-458">NUMERIC_SCALE</span></span>|<span data-ttu-id="0c696-459">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-459">Int16</span></span>|  
|<span data-ttu-id="0c696-460">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-460">DESCRIPTION</span></span>|<span data-ttu-id="0c696-461">String</span><span class="sxs-lookup"><span data-stu-id="0c696-461">String</span></span>|  
|<span data-ttu-id="0c696-462">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0c696-462">OVERLOAD</span></span>|<span data-ttu-id="0c696-463">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-463">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0c696-464">Vistas</span><span class="sxs-lookup"><span data-stu-id="0c696-464">Views</span></span>  
  
|<span data-ttu-id="0c696-465">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-465">ColumnName</span></span>|<span data-ttu-id="0c696-466">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-466">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-467">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-467">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-468">String</span><span class="sxs-lookup"><span data-stu-id="0c696-468">String</span></span>|  
|<span data-ttu-id="0c696-469">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-469">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-470">String</span><span class="sxs-lookup"><span data-stu-id="0c696-470">String</span></span>|  
|<span data-ttu-id="0c696-471">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-471">TABLE_NAME</span></span>|<span data-ttu-id="0c696-472">String</span><span class="sxs-lookup"><span data-stu-id="0c696-472">String</span></span>|  
|<span data-ttu-id="0c696-473">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0c696-473">VIEW_DEFINITION</span></span>|<span data-ttu-id="0c696-474">String</span><span class="sxs-lookup"><span data-stu-id="0c696-474">String</span></span>|  
|<span data-ttu-id="0c696-475">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-475">CHECK_OPTION</span></span>|<span data-ttu-id="0c696-476">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-476">Boolean</span></span>|  
|<span data-ttu-id="0c696-477">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-477">IS_UPDATABLE</span></span>|<span data-ttu-id="0c696-478">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-478">Boolean</span></span>|  
|<span data-ttu-id="0c696-479">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-479">DESCRIPTION</span></span>|<span data-ttu-id="0c696-480">String</span><span class="sxs-lookup"><span data-stu-id="0c696-480">String</span></span>|  
|<span data-ttu-id="0c696-481">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-481">DATE_CREATED</span></span>|<span data-ttu-id="0c696-482">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-482">DateTime</span></span>|  
|<span data-ttu-id="0c696-483">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-483">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-484">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-484">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0c696-485">Índices</span><span class="sxs-lookup"><span data-stu-id="0c696-485">Indexes</span></span>  
  
|<span data-ttu-id="0c696-486">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-486">ColumnName</span></span>|<span data-ttu-id="0c696-487">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-487">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-488">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-488">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-489">String</span><span class="sxs-lookup"><span data-stu-id="0c696-489">String</span></span>|  
|<span data-ttu-id="0c696-490">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-490">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-491">String</span><span class="sxs-lookup"><span data-stu-id="0c696-491">String</span></span>|  
|<span data-ttu-id="0c696-492">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-492">TABLE_NAME</span></span>|<span data-ttu-id="0c696-493">String</span><span class="sxs-lookup"><span data-stu-id="0c696-493">String</span></span>|  
|<span data-ttu-id="0c696-494">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-494">INDEX_CATALOG</span></span>|<span data-ttu-id="0c696-495">String</span><span class="sxs-lookup"><span data-stu-id="0c696-495">String</span></span>|  
|<span data-ttu-id="0c696-496">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-496">INDEX_SCHEMA</span></span>|<span data-ttu-id="0c696-497">String</span><span class="sxs-lookup"><span data-stu-id="0c696-497">String</span></span>|  
|<span data-ttu-id="0c696-498">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-498">INDEX_NAME</span></span>|<span data-ttu-id="0c696-499">String</span><span class="sxs-lookup"><span data-stu-id="0c696-499">String</span></span>|  
|<span data-ttu-id="0c696-500">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0c696-500">PRIMARY_KEY</span></span>|<span data-ttu-id="0c696-501">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-501">Boolean</span></span>|  
|<span data-ttu-id="0c696-502">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0c696-502">UNIQUE</span></span>|<span data-ttu-id="0c696-503">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-503">Boolean</span></span>|  
|<span data-ttu-id="0c696-504">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0c696-504">CLUSTERED</span></span>|<span data-ttu-id="0c696-505">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-505">Boolean</span></span>|  
|<span data-ttu-id="0c696-506">TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-506">TYPE</span></span>|<span data-ttu-id="0c696-507">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-507">Int32</span></span>|  
|<span data-ttu-id="0c696-508">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0c696-508">FILL_FACTOR</span></span>|<span data-ttu-id="0c696-509">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-509">Int32</span></span>|  
|<span data-ttu-id="0c696-510">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0c696-510">INITIAL_SIZE</span></span>|<span data-ttu-id="0c696-511">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-511">Int32</span></span>|  
|<span data-ttu-id="0c696-512">NULLS</span><span class="sxs-lookup"><span data-stu-id="0c696-512">NULLS</span></span>|<span data-ttu-id="0c696-513">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-513">Int32</span></span>|  
|<span data-ttu-id="0c696-514">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0c696-514">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0c696-515">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-515">Boolean</span></span>|  
|<span data-ttu-id="0c696-516">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0c696-516">AUTO_UPDATE</span></span>|<span data-ttu-id="0c696-517">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-517">Boolean</span></span>|  
|<span data-ttu-id="0c696-518">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-518">NULL_COLLATION</span></span>|<span data-ttu-id="0c696-519">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-519">Int32</span></span>|  
|<span data-ttu-id="0c696-520">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-520">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-521">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-521">Int64</span></span>|  
|<span data-ttu-id="0c696-522">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-522">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-523">String</span><span class="sxs-lookup"><span data-stu-id="0c696-523">String</span></span>|  
|<span data-ttu-id="0c696-524">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-524">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-525">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-525">Guid</span></span>|  
|<span data-ttu-id="0c696-526">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-526">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-527">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-527">Int64</span></span>|  
|<span data-ttu-id="0c696-528">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-528">COLLATION</span></span>|<span data-ttu-id="0c696-529">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-529">Int16</span></span>|  
|<span data-ttu-id="0c696-530">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0c696-530">CARDINALITY</span></span>|<span data-ttu-id="0c696-531">Decimal</span><span class="sxs-lookup"><span data-stu-id="0c696-531">Decimal</span></span>|  
|<span data-ttu-id="0c696-532">PAGES</span><span class="sxs-lookup"><span data-stu-id="0c696-532">PAGES</span></span>|<span data-ttu-id="0c696-533">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-533">Int32</span></span>|  
|<span data-ttu-id="0c696-534">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0c696-534">FILTER_CONDITION</span></span>|<span data-ttu-id="0c696-535">String</span><span class="sxs-lookup"><span data-stu-id="0c696-535">String</span></span>|  
|<span data-ttu-id="0c696-536">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0c696-536">INTEGRATED</span></span>|<span data-ttu-id="0c696-537">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-537">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="0c696-538">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="0c696-538">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="0c696-539">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="0c696-539">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="0c696-540">Tablas</span><span class="sxs-lookup"><span data-stu-id="0c696-540">Tables</span></span>  
  
- <span data-ttu-id="0c696-541">Columnas</span><span class="sxs-lookup"><span data-stu-id="0c696-541">Columns</span></span>  
  
- <span data-ttu-id="0c696-542">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c696-542">Procedures</span></span>  
  
- <span data-ttu-id="0c696-543">Vistas</span><span class="sxs-lookup"><span data-stu-id="0c696-543">Views</span></span>  
  
- <span data-ttu-id="0c696-544">Índices</span><span class="sxs-lookup"><span data-stu-id="0c696-544">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0c696-545">Tablas</span><span class="sxs-lookup"><span data-stu-id="0c696-545">Tables</span></span>  
  
|<span data-ttu-id="0c696-546">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-546">ColumnName</span></span>|<span data-ttu-id="0c696-547">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-547">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-548">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-548">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-549">String</span><span class="sxs-lookup"><span data-stu-id="0c696-549">String</span></span>|  
|<span data-ttu-id="0c696-550">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-550">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-551">String</span><span class="sxs-lookup"><span data-stu-id="0c696-551">String</span></span>|  
|<span data-ttu-id="0c696-552">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-552">TABLE_NAME</span></span>|<span data-ttu-id="0c696-553">String</span><span class="sxs-lookup"><span data-stu-id="0c696-553">String</span></span>|  
|<span data-ttu-id="0c696-554">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-554">TABLE_TYPE</span></span>|<span data-ttu-id="0c696-555">String</span><span class="sxs-lookup"><span data-stu-id="0c696-555">String</span></span>|  
|<span data-ttu-id="0c696-556">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-556">TABLE_GUID</span></span>|<span data-ttu-id="0c696-557">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-557">Guid</span></span>|  
|<span data-ttu-id="0c696-558">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-558">DESCRIPTION</span></span>|<span data-ttu-id="0c696-559">String</span><span class="sxs-lookup"><span data-stu-id="0c696-559">String</span></span>|  
|<span data-ttu-id="0c696-560">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-560">TABLE_PROPID</span></span>|<span data-ttu-id="0c696-561">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-561">Int64</span></span>|  
|<span data-ttu-id="0c696-562">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-562">DATE_CREATED</span></span>|<span data-ttu-id="0c696-563">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-563">DateTime</span></span>|  
|<span data-ttu-id="0c696-564">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-564">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-565">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-565">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0c696-566">Columnas</span><span class="sxs-lookup"><span data-stu-id="0c696-566">Columns</span></span>  
  
|<span data-ttu-id="0c696-567">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-567">ColumnName</span></span>|<span data-ttu-id="0c696-568">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-568">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-569">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-569">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-570">String</span><span class="sxs-lookup"><span data-stu-id="0c696-570">String</span></span>|  
|<span data-ttu-id="0c696-571">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-571">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-572">String</span><span class="sxs-lookup"><span data-stu-id="0c696-572">String</span></span>|  
|<span data-ttu-id="0c696-573">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-573">TABLE_NAME</span></span>|<span data-ttu-id="0c696-574">String</span><span class="sxs-lookup"><span data-stu-id="0c696-574">String</span></span>|  
|<span data-ttu-id="0c696-575">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-575">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-576">String</span><span class="sxs-lookup"><span data-stu-id="0c696-576">String</span></span>|  
|<span data-ttu-id="0c696-577">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-577">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-578">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-578">Guid</span></span>|  
|<span data-ttu-id="0c696-579">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-579">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-580">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-580">Int64</span></span>|  
|<span data-ttu-id="0c696-581">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-581">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-582">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-582">Int64</span></span>|  
|<span data-ttu-id="0c696-583">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-583">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0c696-584">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-584">Boolean</span></span>|  
|<span data-ttu-id="0c696-585">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c696-585">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0c696-586">String</span><span class="sxs-lookup"><span data-stu-id="0c696-586">String</span></span>|  
|<span data-ttu-id="0c696-587">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0c696-587">COLUMN_FLAGS</span></span>|<span data-ttu-id="0c696-588">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-588">Int64</span></span>|  
|<span data-ttu-id="0c696-589">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-589">IS_NULLABLE</span></span>|<span data-ttu-id="0c696-590">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-590">Boolean</span></span>|  
|<span data-ttu-id="0c696-591">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-591">DATA_TYPE</span></span>|<span data-ttu-id="0c696-592">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-592">Int32</span></span>|  
|<span data-ttu-id="0c696-593">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-593">TYPE_GUID</span></span>|<span data-ttu-id="0c696-594">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-594">Guid</span></span>|  
|<span data-ttu-id="0c696-595">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-595">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0c696-596">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-596">Int64</span></span>|  
|<span data-ttu-id="0c696-597">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0c696-597">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0c696-598">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-598">Int64</span></span>|  
|<span data-ttu-id="0c696-599">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-599">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0c696-600">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-600">Int32</span></span>|  
|<span data-ttu-id="0c696-601">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0c696-601">NUMERIC_SCALE</span></span>|<span data-ttu-id="0c696-602">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-602">Int16</span></span>|  
|<span data-ttu-id="0c696-603">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0c696-603">DATETIME_PRECISION</span></span>|<span data-ttu-id="0c696-604">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-604">Int64</span></span>|  
|<span data-ttu-id="0c696-605">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-605">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0c696-606">String</span><span class="sxs-lookup"><span data-stu-id="0c696-606">String</span></span>|  
|<span data-ttu-id="0c696-607">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-607">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0c696-608">String</span><span class="sxs-lookup"><span data-stu-id="0c696-608">String</span></span>|  
|<span data-ttu-id="0c696-609">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-609">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0c696-610">String</span><span class="sxs-lookup"><span data-stu-id="0c696-610">String</span></span>|  
|<span data-ttu-id="0c696-611">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-611">COLLATION_CATALOG</span></span>|<span data-ttu-id="0c696-612">String</span><span class="sxs-lookup"><span data-stu-id="0c696-612">String</span></span>|  
|<span data-ttu-id="0c696-613">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-613">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0c696-614">String</span><span class="sxs-lookup"><span data-stu-id="0c696-614">String</span></span>|  
|<span data-ttu-id="0c696-615">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-615">COLLATION_NAME</span></span>|<span data-ttu-id="0c696-616">String</span><span class="sxs-lookup"><span data-stu-id="0c696-616">String</span></span>|  
|<span data-ttu-id="0c696-617">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-617">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0c696-618">String</span><span class="sxs-lookup"><span data-stu-id="0c696-618">String</span></span>|  
|<span data-ttu-id="0c696-619">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-619">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0c696-620">String</span><span class="sxs-lookup"><span data-stu-id="0c696-620">String</span></span>|  
|<span data-ttu-id="0c696-621">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-621">DOMAIN_NAME</span></span>|<span data-ttu-id="0c696-622">String</span><span class="sxs-lookup"><span data-stu-id="0c696-622">String</span></span>|  
|<span data-ttu-id="0c696-623">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-623">DESCRIPTION</span></span>|<span data-ttu-id="0c696-624">String</span><span class="sxs-lookup"><span data-stu-id="0c696-624">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0c696-625">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c696-625">Procedures</span></span>  
  
|<span data-ttu-id="0c696-626">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-626">ColumnName</span></span>|<span data-ttu-id="0c696-627">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-627">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-628">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-628">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0c696-629">String</span><span class="sxs-lookup"><span data-stu-id="0c696-629">String</span></span>|  
|<span data-ttu-id="0c696-630">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-630">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0c696-631">String</span><span class="sxs-lookup"><span data-stu-id="0c696-631">String</span></span>|  
|<span data-ttu-id="0c696-632">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-632">PROCEDURE_NAME</span></span>|<span data-ttu-id="0c696-633">String</span><span class="sxs-lookup"><span data-stu-id="0c696-633">String</span></span>|  
|<span data-ttu-id="0c696-634">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-634">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0c696-635">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-635">Int16</span></span>|  
|<span data-ttu-id="0c696-636">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0c696-636">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0c696-637">String</span><span class="sxs-lookup"><span data-stu-id="0c696-637">String</span></span>|  
|<span data-ttu-id="0c696-638">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-638">DESCRIPTION</span></span>|<span data-ttu-id="0c696-639">String</span><span class="sxs-lookup"><span data-stu-id="0c696-639">String</span></span>|  
|<span data-ttu-id="0c696-640">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-640">DATE_CREATED</span></span>|<span data-ttu-id="0c696-641">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-641">DateTime</span></span>|  
|<span data-ttu-id="0c696-642">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-642">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-643">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-643">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0c696-644">Vistas</span><span class="sxs-lookup"><span data-stu-id="0c696-644">Views</span></span>  
  
|<span data-ttu-id="0c696-645">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-645">ColumnName</span></span>|<span data-ttu-id="0c696-646">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-646">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-647">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-647">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-648">String</span><span class="sxs-lookup"><span data-stu-id="0c696-648">String</span></span>|  
|<span data-ttu-id="0c696-649">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-649">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-650">String</span><span class="sxs-lookup"><span data-stu-id="0c696-650">String</span></span>|  
|<span data-ttu-id="0c696-651">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-651">TABLE_NAME</span></span>|<span data-ttu-id="0c696-652">String</span><span class="sxs-lookup"><span data-stu-id="0c696-652">String</span></span>|  
|<span data-ttu-id="0c696-653">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0c696-653">VIEW_DEFINITION</span></span>|<span data-ttu-id="0c696-654">String</span><span class="sxs-lookup"><span data-stu-id="0c696-654">String</span></span>|  
|<span data-ttu-id="0c696-655">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-655">CHECK_OPTION</span></span>|<span data-ttu-id="0c696-656">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-656">Boolean</span></span>|  
|<span data-ttu-id="0c696-657">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="0c696-657">IS_UPDATABLE</span></span>|<span data-ttu-id="0c696-658">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-658">Boolean</span></span>|  
|<span data-ttu-id="0c696-659">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c696-659">DESCRIPTION</span></span>|<span data-ttu-id="0c696-660">String</span><span class="sxs-lookup"><span data-stu-id="0c696-660">String</span></span>|  
|<span data-ttu-id="0c696-661">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0c696-661">DATE_CREATED</span></span>|<span data-ttu-id="0c696-662">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-662">DateTime</span></span>|  
|<span data-ttu-id="0c696-663">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0c696-663">DATE_MODIFIED</span></span>|<span data-ttu-id="0c696-664">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c696-664">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0c696-665">Índices</span><span class="sxs-lookup"><span data-stu-id="0c696-665">Indexes</span></span>  
  
|<span data-ttu-id="0c696-666">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0c696-666">ColumnName</span></span>|<span data-ttu-id="0c696-667">DataType</span><span class="sxs-lookup"><span data-stu-id="0c696-667">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0c696-668">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-668">TABLE_CATALOG</span></span>|<span data-ttu-id="0c696-669">String</span><span class="sxs-lookup"><span data-stu-id="0c696-669">String</span></span>|  
|<span data-ttu-id="0c696-670">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-670">TABLE_SCHEMA</span></span>|<span data-ttu-id="0c696-671">String</span><span class="sxs-lookup"><span data-stu-id="0c696-671">String</span></span>|  
|<span data-ttu-id="0c696-672">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-672">TABLE_NAME</span></span>|<span data-ttu-id="0c696-673">String</span><span class="sxs-lookup"><span data-stu-id="0c696-673">String</span></span>|  
|<span data-ttu-id="0c696-674">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0c696-674">INDEX_CATALOG</span></span>|<span data-ttu-id="0c696-675">String</span><span class="sxs-lookup"><span data-stu-id="0c696-675">String</span></span>|  
|<span data-ttu-id="0c696-676">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0c696-676">INDEX_SCHEMA</span></span>|<span data-ttu-id="0c696-677">String</span><span class="sxs-lookup"><span data-stu-id="0c696-677">String</span></span>|  
|<span data-ttu-id="0c696-678">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-678">INDEX_NAME</span></span>|<span data-ttu-id="0c696-679">String</span><span class="sxs-lookup"><span data-stu-id="0c696-679">String</span></span>|  
|<span data-ttu-id="0c696-680">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0c696-680">PRIMARY_KEY</span></span>|<span data-ttu-id="0c696-681">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-681">Boolean</span></span>|  
|<span data-ttu-id="0c696-682">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0c696-682">UNIQUE</span></span>|<span data-ttu-id="0c696-683">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-683">Boolean</span></span>|  
|<span data-ttu-id="0c696-684">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0c696-684">CLUSTERED</span></span>|<span data-ttu-id="0c696-685">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-685">Boolean</span></span>|  
|<span data-ttu-id="0c696-686">TYPE</span><span class="sxs-lookup"><span data-stu-id="0c696-686">TYPE</span></span>|<span data-ttu-id="0c696-687">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-687">Int32</span></span>|  
|<span data-ttu-id="0c696-688">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0c696-688">FILL_FACTOR</span></span>|<span data-ttu-id="0c696-689">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-689">Int32</span></span>|  
|<span data-ttu-id="0c696-690">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0c696-690">INITIAL_SIZE</span></span>|<span data-ttu-id="0c696-691">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-691">Int32</span></span>|  
|<span data-ttu-id="0c696-692">NULLS</span><span class="sxs-lookup"><span data-stu-id="0c696-692">NULLS</span></span>|<span data-ttu-id="0c696-693">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-693">Int32</span></span>|  
|<span data-ttu-id="0c696-694">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0c696-694">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0c696-695">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-695">Boolean</span></span>|  
|<span data-ttu-id="0c696-696">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0c696-696">AUTO_UPDATE</span></span>|<span data-ttu-id="0c696-697">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-697">Boolean</span></span>|  
|<span data-ttu-id="0c696-698">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-698">NULL_COLLATION</span></span>|<span data-ttu-id="0c696-699">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-699">Int32</span></span>|  
|<span data-ttu-id="0c696-700">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0c696-700">ORDINAL_POSITION</span></span>|<span data-ttu-id="0c696-701">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-701">Int64</span></span>|  
|<span data-ttu-id="0c696-702">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0c696-702">COLUMN_NAME</span></span>|<span data-ttu-id="0c696-703">String</span><span class="sxs-lookup"><span data-stu-id="0c696-703">String</span></span>|  
|<span data-ttu-id="0c696-704">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0c696-704">COLUMN_GUID</span></span>|<span data-ttu-id="0c696-705">Guid</span><span class="sxs-lookup"><span data-stu-id="0c696-705">Guid</span></span>|  
|<span data-ttu-id="0c696-706">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0c696-706">COLUMN_PROPID</span></span>|<span data-ttu-id="0c696-707">Int64</span><span class="sxs-lookup"><span data-stu-id="0c696-707">Int64</span></span>|  
|<span data-ttu-id="0c696-708">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0c696-708">COLLATION</span></span>|<span data-ttu-id="0c696-709">Int16</span><span class="sxs-lookup"><span data-stu-id="0c696-709">Int16</span></span>|  
|<span data-ttu-id="0c696-710">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0c696-710">CARDINALITY</span></span>|<span data-ttu-id="0c696-711">Decimal</span><span class="sxs-lookup"><span data-stu-id="0c696-711">Decimal</span></span>|  
|<span data-ttu-id="0c696-712">PAGES</span><span class="sxs-lookup"><span data-stu-id="0c696-712">PAGES</span></span>|<span data-ttu-id="0c696-713">Int32</span><span class="sxs-lookup"><span data-stu-id="0c696-713">Int32</span></span>|  
|<span data-ttu-id="0c696-714">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0c696-714">FILTER_CONDITION</span></span>|<span data-ttu-id="0c696-715">String</span><span class="sxs-lookup"><span data-stu-id="0c696-715">String</span></span>|  
|<span data-ttu-id="0c696-716">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0c696-716">INTEGRATED</span></span>|<span data-ttu-id="0c696-717">Boolean</span><span class="sxs-lookup"><span data-stu-id="0c696-717">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c696-718">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c696-718">See also</span></span>

- [<span data-ttu-id="0c696-719">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0c696-719">ADO.NET Overview</span></span>](ado-net-overview.md)

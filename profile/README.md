# OCO-SAC

The **OCO Science Applications and Partnerships Center** brings together software and workflows supporting OCO science and applications. Our work also builds on shared tools maintained across the broader research community.

[Learn more about the center](https://oco.caltech.edu/).

## OCO-SAC projects

| Repository | Role in our work |
| --- | --- |
| [OCO-dashboard](https://github.com/OCO-SAC/OCO-dashboard) (access required) | Prototype dashboard of daily OCO-2 and OCO-3 XCO₂ and solar-induced fluorescence (SIF): interactive maps, regional time series, and diagnostics. |
| [OCO-AppCenter](https://github.com/OCO-SAC/OCO-AppCenter) (access required) | Platform to host and serve OCO data products and visualizations, including the operational OCO dashboard. |

Repositories marked "(access required)" are private; their links work for collaborators with access.

## Related software

The following repositories are maintained outside OCO-SAC and support our analysis, modeling, and visualization workflows.

| Repository | Role in our work |
| --- | --- |
| [AtmosTransport.jl](https://github.com/RemoteSensingTools/AtmosTransport.jl) | Simulate atmospheric CO₂ and tracer transport to connect surface fluxes with atmospheric observations. |
| [SatelliteGridding.jl](https://github.com/cfranken/SatelliteGridding) | Aggregate satellite Level-2 observations onto regular grids, accounting for observation footprints, for mapping and comparison. |
| [vSmartMOM.jl](https://github.com/RemoteSensingTools/vSmartMOM.jl) | Model atmospheric radiative transfer, including gas absorption, scattering, and polarization, to support retrieval development and sensitivity studies. |

## Third-party software

OCO-AppCenter is built from established open-source projects.

| Software | Role in our work |
| --- | --- |
| [eoAPI](https://eoapi.dev) | Foundation for the catalog, API, and tile services below. |
| [pgSTAC](https://github.com/stac-utils/pgstac) and [stac-fastapi-pgstac](https://github.com/stac-utils/stac-fastapi-pgstac) | STAC catalog and API for searching products, versions, and provenance. |
| [titiler-pgstac](https://github.com/stac-utils/titiler-pgstac) and [titiler.xarray](https://github.com/developmentseed/titiler) | Map tiles rendered on demand, for web maps and GIS tools. |
| [STAC Browser](https://github.com/radiantearth/stac-browser) | Web interface for browsing the catalog. |
| [Prefect](https://www.prefect.io) | Orchestrate and monitor pipelines on the SAC server, workstations, SLURM clusters, and GPU machines. |
| [Zarr](https://zarr.dev) and [Apache Parquet](https://parquet.apache.org) / [GeoParquet](https://geoparquet.org) | Storage formats for gridded products and for soundings and tables, both readable in pieces over HTTP. |
| [Xarray](https://xarray.dev), [Dask](https://www.dask.org), [NumPy](https://numpy.org), [pandas](https://pandas.pydata.org), [Apache Arrow](https://arrow.apache.org) | Data processing in the Python pipelines. |
| [earthaccess](https://earthaccess.readthedocs.io) | Download NASA data from GES DISC. |
| [Julia](https://julialang.org) with [Zarr.jl](https://github.com/JuliaIO/Zarr.jl) | Science computation, in the researchers' own packages. |
| [nginx](https://nginx.org) | Gateway and file server for published data. |
| [PostgreSQL](https://www.postgresql.org) / [PostGIS](https://postgis.net) | Database behind the catalog and the orchestrator. |
| [Docker](https://www.docker.com) or [Podman](https://podman.io) with Compose | Package and run the whole stack, on a laptop or the server. |
| [zarrita.js](https://github.com/manzt/zarrita.js), [hyparquet](https://github.com/hyparam/hyparquet), [Apache ECharts](https://echarts.apache.org), [D3](https://d3js.org) | Dashboard maps and charts, drawn in the browser directly from the published files. |

## Data sources

OCO-AppCenter's products, including the dashboard's data, are derived from these upstream datasets.
The original files are kept, so every product can be traced back to its exact inputs.

| Dataset | Provider | Role in our work |
| --- | --- | --- |
| OCO-2 L2 Lite FP (`OCO2_L2_Lite_FP`) | NASA GES DISC | Bias-corrected XCO₂ soundings, for gridded maps and time series. |
| OCO-2 L2 Lite SIF (`OCO2_L2_Lite_SIF`) | NASA GES DISC | SIF retrievals; gridded SIF composites and the basis for GPP products. |
| OCO-3 L2 Lite FP (`OCO3_L2_Lite_FP`) | NASA GES DISC | XCO₂ soundings from the ISS instrument. |
| OCO-3 L2 Lite SIF (`OCO3_L2_Lite_SIF`) | NASA GES DISC | SIF retrievals from the ISS instrument. |
| OCO-2 and OCO-3 L2 Forward SIF (`OCO2_L2_Fwd_SIF`, `OCO3_L2_Fwd_SIF`) | NASA GES DISC | Preliminary SIF for recent days, until the Lite files arrive. |
| TROPOMI SIF, TROPOSIF L2B (`L2B_SIF___`) | ESA [Sentinel-5P Product Algorithm Laboratory](https://data-portal.s5p-pal.com) (S5P-PAL) | Independent, denser SIF record for comparison with OCO. |
| NOAA surface-flask CO₂ | [NOAA Global Monitoring Laboratory](https://gml.noaa.gov) (GML) | In-situ surface CO₂, shown alongside XCO₂ in the dashboard. |
| GISTEMP v4 | [NASA Goddard Institute for Space Studies](https://data.giss.nasa.gov/gistemp/) (GISS) | Surface-temperature anomalies for the dashboard. |

Further inputs, for new dashboard panels and for flux inversions, will be listed here as those
pipelines come online.

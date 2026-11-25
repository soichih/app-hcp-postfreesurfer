<h1 align="center">HCP Pipeline (PostFreeSurfer)</h1>

<p align="center">
  BIDS app for HCP post-FreeSurfer for BrainLife.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/bl.app.80"><img src="https://img.shields.io/badge/Brainlife-bl.app.80-blue.svg" alt="Run on brainlife.io"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **BIDS app for HCP post-FreeSurfer for BrainLife.**

BIDS app for HCP post-FreeSurfer for BrainLife. Outputs include surface topologies and features resampled onto the high (164k) dimensional atlas space as well as myelin mappings. (Please see https://github.com/Washington-University/HCPpipelines/wiki/v3.4.0-Release-Notes,-Installation,-and-Usage#structural-preprocessing for more information on HCP structural pipelines.)

| | |
|---|---|
| **Inputs** | `neuro/freesurfer` · `neuro/hcp/freesurferpre` |
| **Outputs** | `raw` |
| **Container** | `brainlife/hcppipeline:0.1` |
| **Resources** | 8 CPUs · 24 h walltime |
| **Requires** | `FREESURFER_LICENSE` |
| **Run it** | [doi.org/10.25663/bl.app.80](https://doi.org/10.25663/bl.app.80) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `freesurfer` | `neuro/freesurfer` (v5) | yes | FreeSurfer directories |
| `hcp_freesurferpre` | `neuro/hcp/freesurferpre` | yes | Output from HCP PreFreeSurfer |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `HCP_postFS` | `raw` |  |

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/bl.app.80](https://doi.org/10.25663/bl.app.80), choose `neuro/freesurfer`, `neuro/hcp/freesurferpre` from your project and press **Execute**. The results are saved to your project as `raw`.

### Locally

You need [Singularity/Apptainer](https://apptainer.org/) (the App runs in `brainlife/hcppipeline:0.1`), [`jq`](https://jqlang.github.io/jq/), `FREESURFER_LICENSE`.

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "freesurfer": "/path/to/freesurfer/freesurfer",
       "hcp_freesurferpre": "/path/to/hcp_freesurferpre/hcp_freesurferpre"
   }
   ```

3. Run `./main`.

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- HCP Pipeline (PostFreeSurfer). brainlife.io App. [doi:10.25663/bl.app.80](https://doi.org/10.25663/bl.app.80)
- Fischl. FreeSurfer. *NeuroImage* 62:774-781 (2012). [doi:10.1016/j.neuroimage.2012.01.021](https://doi.org/10.1016/j.neuroimage.2012.01.021)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

Maintained by [@soichih](https://github.com/soichih).

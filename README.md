A simple portfolio site built with Jekyll and the Minimal Mistakes theme.
Documentation:
- [Jekyll](https://jekyllrb.com/)
- [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) | [GitHub](https://github.com/mmistakes/minimal-mistakes)

## Dev Setup (ARCH)

```
sudo pacman -S ruby base-devel python-pip
export PATH="$HOME/.local/share/gem/ruby/3.4.0/bin:$PATH"
source ~/.bashrc
gem install jekyll bundler erb
bundle config set --local path 'vendor/bundle'
bundle install
bundle exec jekyll serve
```

The project will be served on `http://localhost:4000`

## Project Structure

```
portfolio-site/
|-- index.md                        # About/Landing page (site.com)
|-- resume.md                       # Resume page (site.com/resume)
|-- projects/
|   |-- index.md                    # Projects landing (site.com/projects)
|   |-- graphics.md                 # site.com/projects/graphics
|   |-- photography.md              # site.com/projects/photography
|   |-- video.md                    # site.com/projects/video
|-- campaigns/
    |-- index.md                    # Campaigns landing (site.com/campaigns)
    |-- lazercon.md                 # site.com/campaigns/lazercon
    |-- advanced-training.md        # site.com/campaigns/advanced-training
    |-- emotional-marketplace.md    # site.com/campaigns/emotional-marketplace
```

## Updating Resume/CV

The resume is generated using RenderCV. Set it up in a Python virtual environment:
```
python -m venv ~/.venv/rendercv
source ~/.venv/rendercv/bin/activate
pip install "rendercv[full]"

# from project root
rendercv render assets/resume/Alicia_Vanderpool_CV.yaml
```

**Note**: You must copy `Alicia_Vanderpool_CV.md` from `assets/resume/rendercv_output` to `_pages` or changes will not be represented on the live site.
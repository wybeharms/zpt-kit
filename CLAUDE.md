# ZPT Kit plugin repo (generated)

This repository distributes the **ZPT Kit** by ZPT Partners as a Claude Code plugin. It is fully generated: the kit's source of truth lives in the private ZPT business repo (`zpt-business`, at `kits/zpt-kit/`), and the script `kits/scripts/publish-plugin.sh` there copies the kit into `plugin/skills/start/` here and pushes.

Never hand-edit `plugin/skills/start/`: the next publish overwrites it. Kit development happens in the source repo, where the kit's own kit-development exception applies. A session opened in this repo should only ever be inspecting or re-publishing, never editing kit content.

Install: `/plugin marketplace add wybeharms/zpt-kit`, then `/plugin install zpt-kit@zpt-partners`. Start it in any folder by saying "start the ZPT Kit" or with `/zpt-kit:start`. More at https://zptpartners.com.

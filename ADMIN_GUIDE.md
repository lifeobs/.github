# lifeobs: admin guide

*Last updated: 28 October 2026 - Amélie Fargevieille*


How we organize the GitHub organization and the Zenodo community.
Intended for owners and repository admins.

## 1. Overview
- **GitHub organization `lifeobs`**: where the team's repositories live.
- **Zenodo community `lifeobs`**: groups the archived releases (DOIs) produced by the team.
- Contacts:
   > Céline Le Bohec - celine.lebohec@cefe.cnrs.fr
   > 
   > Amélie Fargevieille - afargevieille@centrescientifique.mc

## 2. Repository types
| Type | Visibility | Examples |
|---|---|---|
| `article-scripts` | public once ready | scripts of a research article |
| `software` | *access to be defined* | tools used by the team |
| `wiki` | *access to be defined*| dokuwiki |
| `website` | public | team website |
| `template` | public | `template-article-scripts` |

## 3. Naming conventions
- Article repositories: `year-lastname-topic` (lowercase, hyphens, no accents or spaces).
- Topics: lowercase with hyphens. Every article repository gets `article-scripts`
  plus two or three topical keywords.

## 4. Roles and teams
- **Owners**: manage the organization settings and create repositories.
- **Teams**: *to be defined* (access to the wiki and to the software repositories
  is under discussion with the PI).
- **Outside collaborators**: people who work on a single repository.
- Until the teams are defined, access is given per repository by an owner.
- Repository role guide: Write for contributors, Maintain for project leads,
  Admin only for whoever must enable the Zenodo integration (admin rights are required).
- Invitations expire after a few days: check Settings > People > Invitations.

## 5. Creating a new article repository (checklist for owners)
1. Create it from `template-article-scripts` ("Use this template").
2. Name it `year-lastname-topic`; add a one-sentence description.
3. Add topics: `article-scripts` + keywords.
4. Set custom properties: `Type = article-scripts`, `Status = in-progress`, `Year`.
5. Give access to the author(s) with the appropriate role.

## 6. Before a release (checklist)
- [ ] README completed (no placeholders left).
- [ ] `LICENSE` present (GPL-3.0-or-later unless agreed otherwise with the PI).
- [ ] `zenodo.example.json` filled in and renamed to `.zenodo.json`:
      authors and order agreed, no example ORCID or DOI left, valid JSON.
- [ ] `CITATION.example.cff` filled in and renamed to `CITATION.cff` (same title and authors).
- [ ] No sensitive data or credentials in the repository or its history.
- [ ] Community identifier is `lifeobs`.

## 7. Releasing on Zenodo
1. Zenodo > GitHub settings: sync, then switch the repository on (needs admin rights
   and a public repository).
2. Create a release on GitHub (tag such as `v1.0.0`).
3. Check the new Zenodo record, then accept the inclusion request in the community.
4. A published record cannot be deleted: corrections go through "Edit" (metadata)
   or a new release (files).

## 8. After the article is published
- In Zenodo ("Edit"): add the DOI of the article (and of the dataset if relevant).
- In the repository: update `.zenodo.json`, `CITATION.cff` (`preferred-citation`)
  and the README (DOI badge), so that GitHub and Zenodo stay consistent.
- Update the properties: `Status = published`, `Year`.

## 9. Joining and leaving the team
- Onboarding: invite to the organization or as outside collaborator; add to teams.
- Offboarding: remove from teams and repositories; transfer ownership of anything they created.
- Keep at least two owners; two-factor authentication is required.

## 10. Useful links
- GitHub organization: https://github.com/lifeobs/
- Zenodo community: https://zenodo.org/communities/lifeobs/
- Template repository: https://github.com/lifeobs/template-article-scripts

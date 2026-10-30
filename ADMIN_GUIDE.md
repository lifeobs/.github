# lifeobs: admin guide

*Last updated: 28 October 2026 - Amélie Fargevieille*


How we organize the GitHub organization and the Zenodo community.
Intended for owners and repository admins.

## 1. Overview
- **GitHub organization `lifeobs`**: where the team's repositories live.
- **Zenodo community `lifeobs`**: groups the archived releases (DOIs) produced by the team.
- Contacts:
   > Céline Le Bohec - celine.lebohec[at]cefe.cnrs.fr
   > 
   > Amélie Fargevieille - afargevieille[at]centrescientifique.mc

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
### 4.1 Organization roles
- **Owner**: manages the organization settings and teams, creates repositories
  (for now, only owners create repositories) and can change a repository's visibility.
  There must always be at least two owners.
- **Member**: belongs to the organization; access to repositories comes only from teams
  or from permissions given on a repository (base permission is "No permission").

### 4.2 Teams
| Team | Who | Software repositories | Wiki | Article repositories |
|---|---|---|---|---|
| `members` (parent) | Everyone in the team: students, collaborators, field assistants | Read | Write | none by default |
| `software-dev` (child of `members`) | People who maintain the software | Write | Write (inherited) | none by default |

- A child team inherits the access of its parent team.
- A person can belong to several teams.
- Teams are kept "Visible" so that they can be nested.

### 4.3 Article repositories
- A person who starts an article asks an owner to create the repository
  from `template-article-scripts` (named `year-lastname-topic`).
- The owner sets the description, topics and custom properties
  (see the checklist in section 5).
- Access is given **person by person** (Write; Admin only for whoever enables the Zenodo
  integration), not through teams.

### 4.4 Outside collaborators
People who work on a single repository and are not members of the organization
(external collaborators, for example) are added directly to that repository with the
appropriate role (Read or Write).

### 4.5 Onboarding and offboarding
- **Onboarding**: invite the person to the organization (invitations expire after a few
  days: check Settings > People > Invitations), add them to `members`, and to
  `software-dev` only if they maintain software. Add them to article repositories
  individually when they take part in an article.
- **Offboarding**: remove the person from teams and from repositories where they were
  added individually. Check that they have no ongoing release or pending invitation.
- **Review**: check the member list at every change of season or semester.
  Teams do not expire automatically.

### 4.6 Repository role guide
- **Read**: install and read software, read the wiki.
- **Write**: contribute to a repository (article scripts, software, wiki).
- **Maintain**: manage a repository without changing sensitive settings.
- **Admin**: only for whoever must enable the Zenodo integration (admin rights are required).

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

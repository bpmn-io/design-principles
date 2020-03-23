> __Notice:__ This document is a wiki. Help us [and :memo: improve it](https://github.com/bpmn-io/internal-docs/edit/master/design/README.md).

# Design Principles

A summary of some core design principles that are baked into our modeling tools.

## TLDR

* [Editors, not drawing tools](#editors-not-drawing-tools)
* [Less is more](#less-is-more)
* [Know the context](#know-the-context)
* [Do the hard work to make it simple](#do-the-hard-work-to-make-it-simple)
* [No surprises](#no-surprises)
* [Empower the user](#empower-the-user)

## Editors, not drawing tools

Our editors are domain specific tools with a strong foundation on the standards they support.

### Examples

* __We ensure diagrams are always structurally consistent__ (no free floating sequence flows, can be exported to a valid standards representation at any point in time).
* __We build upon domain specific modeling rules__ (no tasks in tasks, [no sequence flows across pool boundaries](./images/seq-message-flow.gif)).
* __We do not support intermediate states__, if they are without representation in target language (free floating connections).
* __We support users to ensure diagrams stay semantically sound__ (change sequence to message flows and vice versa, ...).
* __We enforce and/or embrace domain specific modeling conventions__ ([left-to-right](./images/auto-place.gif), top-to-botton, [encoded good practices](./images/create-sub-process.gif))

### Why

* Guides users in learning and modeling the standards.
* Setup diagrams for interchange and basic understandability.
* Prevent unintentional human harm.


## Less is more

Our tools are intentionally minimalistic.

### Examples

* __We build upon a minimal set of core modeling concepts__.
    * Create special elements [via the palette](./images/palette.png)
    * continue modeling [via the context-pad](./images/context-pad.png)
    * change elements [via the morph menu](./images/morph-menu.png)
* __We expose only a small amount of things to do next__ (see also [:arrow_right: know the context](#know-the-context)).

### Why

* Reduces the cognitive burden for newcomers and experienced users alike.
* Aids modeling in collaborative environments where different perspectives / tool / modeling experience clashes.
* Compensates for the standards being overly complicated at times

## Know the context

We understand that using our tools is highly situational, depending on what the user wants to achieve. We provide intuitive means that support users across all stages of diagram editing.

### Examples

* __We embrace continues modeling / locality__ (cf. [context pad](./images/context-pad.png), infinite canvas).
* __We provide tools for larger scale refactorings__ (i.e. space tool, [drop on flow](./images/drop-on-flow.gif))
* __We provide facilities for efficient navigation and discovery__

### Why

* Get out of the way as a tool.


## Do the hard work to make it simple

We do a lot of things under the hood so the user does not have to.

### Examples

* __We keep the diagram sound, as the user models__ (connection layout and repair on element move, [automatic label move](./images/label-move.gif), infinite canvas and  [automatically origin alignment](./images/align-to-origin.gif)).
* __However, we do NOT overrule the user__. 

### Why

* A user can think about _what_ she would like to express
* Get out of the way as a tool.
* Do not cause frustrating extra work.

See also [:arrow_right: no surprises](#no-surprises).


## No surprises

We aim for predicable, intuitive editing behavior.

### Examples

* __We offer predictable core modeling actions__ ([connect previews](./images/connect-preview.gif), move ghosts)
* __We do repair / fix sensibly during user editing__ (layout / grid snapping / alignment)
* __We clean up / support during local modifications__ (see also [:arrow_right: do the hard work](#do-the-hard-work-to-make-it-simple))
* __We design breaking modeling changes with a migration path in mind__ (e.g. incremental grid snapping)
* __We do NOT globally, magically fix everything__

### Why

* Automagic changes should have the sole purpose of "getting the tool out of the way"
* Predicable behavior is a basis of trust and aids learning


## Empower the user

We do no magic. Using our tools, the user is in control.

### Examples

* __We are agnostic to modeling styles and conventions__ (i.e. spacing). There is not one standard way to model.
* __However, we pickup diagram styles and support users in building consistent looking models__ ([auto-place](./images/auto-place.gif), align / distribute, ...).
* __We are forgiving.__ We rather allow the user to do what he attempts to do than blocking a request. Following up, we do best effort to support her intend and still end up in a valid diagram (drop on flow, change sequence to message flow when moving task across pool boundaries, cf. also [:arrow_right: do the hard work](#do-the-hard-work-to-make-it-simple)).

### Why

* Users should be able to learn the implemented standards by doing
* Users should never be frustrated through changes our tool introduces


## Resources

* [GOV.UK design principles](https://www.gov.uk/guidance/government-design-principles)
* [principles.design](https://principles.design/)



---

How to achieve all this? __Iteration and user feedback.__

Are we done achieving all this? __No.__

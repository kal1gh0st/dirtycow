# dirtycow
Dirty Cow is a silly name, but it's a serious Linux kernel problem. According to the Red Hat bug report, "a race condition was found in the way the Linux kernel's memory subsystem handled the copy-on-write (COW) breakage of private read-only memory mappings. An unprivileged local user could use this flaw to gain write access to otherwise read-only memory mappings and thus increase their privileges on the system."

Dirty Cow Linux Bug
The name is dumb, but the Linux security bug behind it is serious.

Race conditions themselves are common. Barely a month goes by that Windows, for example, doesn't patch one. But common doesn't mean innocuous.

The problem itself, as Linus Torvalds explained, "is an ancient bug that was actually attempted to be fixed once (badly) by me eleven years ago ... but that was then undone due to problems on s390 by [another] commit".

Then, it was hard to get this bug to show itself, but Torvalds continued, "the VM [virtual machine] has become more scalable, and what used a purely theoretical race back then has become easier to trigger."

"To fix it," Torvalds added, "we introduce a new internal FOLL_COW flag to mark the 'yes, we already did a COW,' rather than play racy games."

It's not only become easier to trigger, it's being used in attacks. According to Phil Oester, the Linux security researcher who uncovered it, the exploit is easy to execute and will almost certainly become more widely used. Oester told V3 that "the exploit in the wild is trivial to execute, never fails and has probably been around for years".

Once used, Dirty Cow can pry open Linux systems and give the attacker high levels of access.

Worse still, the attack, in and of itself, doesn't leave traces in the system logs. Some unknown user suddenly doing things that require root privileges are, of course, another matter. But, by then, it's too late.

Attacks based on Dirty Cow don't work on all Linux distributions. For example, Dirty Cow can't make a mess of Red Hat Enterprise Linux (RHEL) 5 or 6. It can, however, maul Fedora and RHEL 7. The best thing to do is to assume that you are vulnerable and patch your system as soon as possible.

Fortunately, patches are now available for most major Linux distributions.

Oh, and one final note, the creators of the Dirty Cow name and logo are well aware that it's kind of a dumb name. They explained, "It would have been fantastic to eschew this ridiculousness, because we all make fun of branded vulnerabilities too, but this was not the right time to make that stand."

So, silly name and all, after reading this article, patch your Linux boxes.

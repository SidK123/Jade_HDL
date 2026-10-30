# Language Features

A couple of features that we know we want for sure:
- First-Class Reduction;
    - I think that reduction is something we do all too much; consider something like an FIR filter where we're averaging over N samples. We just do addition N times and then divide. Wouldn't it be so much better if we had a reduction and we just optimized it as best as we can?
- First-Class Map:
    - Pretty similar reasoning to the one above. 
- Redoing State Machines:
    - Genuinely what are we doing still writing out `next_state = ...`, and casing on `current_state`? Surely there is a better way to describe state machines and keep track of their state without 100s of lines of `always_comb` blocks that are maybe 10 columns wide because of how sparse the code genuinely is.
- Easier Register Generation:
    - `always_ff` blocks with one or two `if` statements in the middle are going to be a thing of the past. Why do we have two variables named almost the same thing, with different prefixes, tied together in one `always_ff` block just to generate a registered version? Why can't we do this shit during declaration with an annotation or something like that? 
- Lambdas for `always_ff`:
    - Another idea is to just have 'registered lambdas'. Need to think about this one a bit more.

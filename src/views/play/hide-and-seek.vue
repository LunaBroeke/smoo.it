<template>
  <smoo-card
    :visible="$attrs.visible"
    accordion="play"
    key="hide-and-seek"
    @show="$emit('show', $event)"
    @hidden="$emit('hidden', $event)"
  >
    <template #header><smoo-role-icon type="seek"/> <b>Hide &amp; Seek</b> game mode</template>
    <p>
      The <b>Hide &amp; Seek</b> game mode was developed by
      <a-ext href="https://github.com/CraftyBoss/SuperMarioOdysseyOnline/" icon="github">CraftyBoss</a-ext>
      and released in 2022 with the first version <code>v1.0.0</code> of the official mod.
    </p>
    <p>
      A kingdom that hasn't been played in is chosen randomly for a new round.
      Some of the players that haven't started a round as a <smoo-role-icon type="seek"/>Seeker before are chosen randomly to be <smoo-role-icon type="seek"/>Seekers for this round.
      (For fairness reasons the amount of <smoo-role-icon type="seek"/>Seekers should be the same in all rounds or might be adjusted to the size of the kingdom.)
    </p>
    <p>
      The <smoo-role-icon type="seek"/>Seekers go into the Odyssey and start to count down for 60 or more seconds.
      The <smoo-role-icon type="hide"/>Hiders run away and look for a place to hide in.
      After the time is up, the <smoo-role-icon type="hide"/>Hiders switch to hider mode (which will unpause their timer) and the <smoo-role-icon type="seek"/>Seekers start seeking them.
      <smoo-role-icon type="hide"/>Hiders can move around at any time whenever they want and aren't limited to the first minute.
      Only <smoo-role-icon type="seek"/>Seekers are allowed to use the checkpoints to warp around.
    </p>
    <p>
      If a <smoo-role-icon type="seek"/>Seeker touches a <smoo-role-icon type="hide"/>Hider, the <smoo-role-icon type="hide"/>Hider dies.
      When a <smoo-role-icon type="hide"/>Hider dies their timer pauses and they become <smoo-role-icon type="seek"/>Seekers.
      Dying within the first few minutes of a round is forgivable, unless while being chased by a <smoo-role-icon type="seek"/>Seeker.
      Once everyone has become a <smoo-role-icon type="seek"/>Seeker, the round is over.
      When everyone has started a round as a <smoo-role-icon type="seek"/>Seeker, the game is over and the player with the highest time wins.
    </p>
    <p>
      After some time in a round - usually every two minutes - <smoo-role-icon type="hide"/>Hiders are obligated to give the <smoo-role-icon type="seek"/>Seekers a hint where they are.
      <smoo-role-icon type="seek"/>Seekers choose what kind of hint to provide.
      Starting with more general hints and as the round goes on more specific hints.
      The hint has to be a truthful statement at the moment given.
      Even if a second later it isn't true anymore.
      Common hints are:
      <br/>
      <ul>
        <li>Being in a sub-area or in the overworld.</li>
        <li>Top or bottom half of the in-game map.</li>
        <li>Left or right half of the in-game map.</li>
        <li>Cell coordinates of the in-game map (e.g. <code>C2</code>).</li>
        <li>Drawing a picture that hints to where they are.</li>
        <li>Sending a cutout of a screenshot.</li>
      </ul>
    </p>
    <p>
      Places that are forbidden to hide in:
      <ul>
        <li>Other kingdoms.</li>
        <li>Inside the Odyssey.</li>
        <li>Inside captures (using static captures like power lines temporarily to move somewhere is fine).</li>
        <li>Inside something without collision that occludes the player completely (e.g. trees).</li>
        <li>At a position where an object was located at before interacting with it (e.g. crates or chests).</li>
        <li>In areas inaccessible by others (e.g. rooms only accessible by wearing specific costumes).</li>
        <li>In special areas (e.g. the boss fight paintings in <code>Mushroom Kingdom</code> or race events like Koopa Freerunning).</li>
        <li>Out of bounds.</li>
      </ul>
    </p>
    <p>
      Kingdom specific rules:
      <ul>
        <li>
          <code>Deep Woods</code> is not considered to be a part of <code>Wooded Kingdom</code>.
          Accidentally falling into it counts as dying.
          It might be used as its own kingdom to play a round in.
        </li>
        <li>
          In <code>Snow Kingdom</code> the hint for sub-area or not is extended by a third option: <code>Shiveria</code>.
          This option aggregates all (sub-)areas that are accessible after falling down the hole.
        </li>
      </ul>
    </p>
    <p>
      Controls:
      <ul>
        <li><smoo-btn L/> + <smoo-btn DLeft/> - Enable/disable the Hide &amp; Seek game mode.</li>
        <li><smoo-btn DUp/> - Switch between <smoo-role-icon type="hide"/>Hider and <smoo-role-icon type="seek"/>Seeker.</li>
        <li>[<smoo-role-icon type="hide"/>Hider] <smoo-btn DLeft/> - Decrease hiding time.</li>
        <li>[<smoo-role-icon type="hide"/>Hider] <smoo-btn DRight/> - Increase hiding time.</li>
        <li>[<smoo-role-icon type="hide"/>Hider] <smoo-btn L/> + <smoo-btn DDown/> - Reset hiding time.</li>
        <li>[Gravity] <smoo-btn L/> + <smoo-btn DRight/> - Toggle gravity camera.</li>
      </ul>
    </p>
    <p>
      Game mode settings in the Hide &amp; Seek config menu:
      <ul>
        <li><b>H&amp;S Gravity</b>: The players gravity changes depending on the ground Mario stands on. E.g. to run on walls.</li>
        <li><b>Mario Collision</b>: Prevents running trough other players.</li>
        <li><b>Mario Bounce</b>: Jumping onto other players bounces the own player upwards.</li>
        <li><b>Cappy Collision</b>: Prevents running trough Cappy from other players.</li>
        <li><b>Cappy Bounce</b>: Jumping onto Cappy from other players bounces the own player upwards.</li>
      </ul>
    </p>
  </smoo-card>
</template>

# The Budyko-Sellers Model

This project is looking at the Energy Budget of the Earth. The diagram below shows an overview of the simplified model used.
<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/energy_budget_earth.png">
</p>

## Part 1: Albedo
To represent the simplified energy budget, a linear energy balance equation is used.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/linear_energy_balance.png" width="500">
</p>

where C is the heat capacity, T is temperature, t is time, S is incoming solar short-wave radiation, α is albedo, and B and A are outgoing longwave radiation. In this model, the rate of change of mean temperature of the Earth is determined by the difference between absorbed solar radiation (after reflection by albedo) and emitted terrestrial radiation. In equilibrium, the incoming and outgoing radiation will be in balance, causing no change in temperature.

The Budyko-Sellers model adds one complication, in that it says albedo is a function of temperature.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/albedo_temp_function.png" width="500">
</p>

The ice line is the average latitude line in the Arctic where ice reaches around the globe. At 0, there is no ice, and at 1, ice covers the planet. As temperature increases, the ice line recedes, and as temperature decreases, the ice line moves southward.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/iceline.png">
</p>

As the ice line moves toward lower latitudes, albedo is higher, reflecting more of the solar incoming radiation. This decreases temperature and further increases area covered with ice, in a positive feedback loop.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/albedo.png">
</p>

Because albedo is affected by temperature, the Budyko-Sellers energy budget requires solving for albedo as a function of temperature in order to observe change in temperatures over time.

## Part 2: Solar Constant

In the Budyko-Sellers model, a solar constant is used. In today's Earth, the solar constant is 1,361 W m⁻². As Earth's elliptical path around the sun changes (on a paleoclimatic timescale), the solar constant can increase or decrease. It has been shown that a decrease in the solar constant is a factor in ice ages, as it feeds into the ice-albedo feedback mechanism described above.

Equilibria represent the states where incoming and outgoing radiation are balanced, so the temperature no longer changes (where the trajectory in the graph below crosses zero). These points are important because they determine the long-term climate states of the system.

Stable equilibria, where the trajectory crosses zero and has a negative slope, are those toward which the system naturally evolves. If we imagine that a ball is on this trajectory, it will naturally settle in the troughs where the slope is negative. If the temperature is perturbed slightly (or the ball is kicked a bit), it will return to equilibrium. Unstable equilibria, where the slope is positve in the graph below, act like tipping points: a small perturbation can drive the system toward a different stable state.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/energy_budget.png">
</p>

At 1412 W m⁻², there are three fixed-point equilibria, two stable and one unstable. At extreme solar constants, equilibria disappear.

One can also show the bifurcation diagram of the solar constant vs. temperature. The diagram below shows two stable states and one 'edge' state, the unstable equilibrium decribed above.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/bifurcation_diagram.png">
</p>

## Part 3: Time Series

Keeping the same three values of solar constant (500, 1412, and 2000 W m⁻²), the graph below is a deterministic time series of temperature which has been run for 200 years. 

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/temperature_over_time.png">
</p>

At a solar constant of 2000 W m⁻², a slight bend appears in the time series. Because at 2000, a bifurcation has occurred (equilibria have disappeared), this is probably a long transient where an equilibrium point used to be (also called a ghost attractor).

## Part 4: The Potential Function

Below, 12 solar constant values have been chosen, and the graph of the potential is shown for each. The potential shows the number of equilibrium points for each solar constant and their stability, as minima correspond to stable equilibrium and maxima correspond to unstable equilibrium. Since the derivative of the potential corresponds to the negative of the system’s rate of change (𝑑𝑉/𝑑𝑇 = −𝑑𝑇/𝑑𝑡), the slope of the potential determines the direction and speed of temperature evolution. The potentials for different solar constants shown below demonstrate a bifurcation occurring: At low solar constant values, no equilibria are present. Increasing the solar constant gives a double well potential, until eventually one, and then both of these equilibria disappear at high solar constants.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_500.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1100.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1200.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1412.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1480.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1500.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1600.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1700.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1800.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_1900.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_2000.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/potential_S0_2500.png" width="400">
</p>

Note that at a solar constant of 1900, the ghost attractor shown in the time series is also present in the graph of the potential.

## Part 5: Noise

In this model, two stable states are observed for many of the solar constant values. But transitions between these states will never occur without extreme external forcing or the addition of noise. Below Gaussian white noise has been simulated to observe transitions between states, shown as an ensemble time series of temperature for each of the 12 solar constant values given above run 30 times with different noise values.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_500.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1100.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1200.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1412.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1480.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1500.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1600.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1700.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1800.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_1900.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_2000.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/timeseries_2500.png" width="400">
</p>

Noise allows transitions in 5 of the time series shown above, corresponding to their double-well potentials. Note that the amplitude of noise controls the amount of fluctuation a given trajectory can have, and fewer fluctuations and therefore, transitions, will be observed with lower amplitude values. The above transitions have been achieved with an amplitude value of 3. Below is a brief outline of transitions observed at different values of noise amplitude. Note that the maximum number of transitions which can be achieved is 30.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/noise_transitions.png" width="800">
</p>

Noisy trajectories allow for statistical analysis for ensemble simulations. With Gaussian white noise, the probability density of the trajectories will have a Gaussian distribution. Where time series have not transitioned, PDFs are unimodal, but where transitions are observed, the PDFs are bi-modal. In cases where a bifurcation has occurred, a ghost attractor can also still be seen in the PDF.

<p>
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_500.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1100.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1200.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1412.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1480.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1500.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1600.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1700.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1800.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_1900.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_2000.png" width="400">
  <img src="https://github.com/amethystaurora-robo/numerical_integration_exercises/blob/main/images/histogram_2500.png" width="400">
</p>

References:

(F. Ragone, personal communication, 2025)

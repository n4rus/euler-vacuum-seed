# Replication protocol (frozen Phi, SPARC)
Data: public SPARC/VizieR J/AJ/152/157 (175 galaxies, 3391 records).
Features (frozen): lL=log10(L3.6/Lsun); eta_HI=(MHI/Msun)/(L3.6/Lsun);
  Upsilon*=0.5 fixed (gas+disk Vbar from SPARC photometry).
Model (frozen, zero per-galaxy params): V=sqrt(Vbar^2+C(L)Phi),
  Phi=sigmoid(0.525*lL+0.242*eta_HI+1.07), C(L)=2800*L^0.525 (L in 1e9 Lsun).
Fit set (15, disclosed): NGC2403 NGC2841 NGC3198 NGC6015 NGC6503 NGC6946
  UGC02953 UGC03205 UGC03580 UGC05253 UGC06787 UGC09133 UGC11914 DDO154 NGC7793
  (13 locus + 2 Phi->0 limits). Split: Train 10 / Val NGC3198,NGC2403 /
  Test UGC03580,DDO154,NGC7793 (untouched during fitting).
Blind: remaining 160 (Nvel>=4) with no refit. Sign test vs Vbar-only.
Files: supplement_residuals.csv (3391 per-point rows: galaxy,r,vbar,vobs,vpred,resid).
Filed: Test RMSE 10.64; blind-160 126/160 (p=6.3e-14); RAR 10.43<12.67;
  NFW blind-30 0/30 (honest loss); intrinsic scatter median 24 km/s.

Misfit convention (defined 2026-10-16, validated by exact reproduction):
  chi_n = sqrt( (1/n) * sum_i [ (Vobs_i - Vpred_i) / max(eV_i, 0.5) ]^2 )
  i.e. point misfit in units of the tabulated velocity error (floor 0.5 km/s),
  RMS-combined. All "RMSE = x.xx" numbers in the papers use this convention
  unless km/s is stated. Reproduction check (this convention, this data):
  Vbar-only all-3391 = 27.51; RAR (g_dag=1.2e-10) all-3391 = 12.67;
  frozen Phi flat all-3391 = 10.32 (0.525 exponent) [10.43 with the pre-freeze
  0.5 exponent]; blind-160: flat 10.02, Yukawa(lambda=1 kpc) 9.45.
  LT per-radius (km/s units): flat 14.9 vs Yukawa 13.0 (337 pts).
